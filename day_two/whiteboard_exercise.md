#Partner A 
`a ||= b`


class WhatIsSelf
  def test
    puts "At the instance level, self is #{self}"
  end

  def self.test
    puts "At the class level, self is #{self}"
  end
end

WhatIsSelf.test
 #=> At the class level, self is WhatIsSelf

WhatIsSelf.new.test
 #=> At the instance level, self is #<WhatIsSelf:0x28190>
```

object = whatIsSelf.new

object.test
WhatIsSelf.test

RSpec.describe Calculator do
  it "add method adds numbers" do
    calc = Calculator.new
    expect(calc.add(3, 4)).to eq(7)
  end
end

super(name, bet)


parking lot 
design OOP 
holistic view of which method sits on each 



purpose of our parking lot program is to keep track of what is parked where, if anything 

parking lot class 
empty grid, two d array 
element = parking space  <--- class 


parking space Class 
[] 

empty? 

add cars 

remove cars 

{}



Music jukebox

virtual 
doesn't take $
class Jukebox


class artist

album [song]


class Jukebox
  attr_accessor :user
  attr_reader :current_track

  def initialize(player, user)
    @player = player
    @user = user
    @current_track = nil
  end
end

class Player
  attr_accessor :album, :playlist

  def initialize(album, playlist)
    @album = album
    @playlist = playlist
  end

  def play_track(track)
    # Begin playing...
  end
end

class Playlist
  def initialize
    @queue = []
  end

  def add_track(track)
    @queue.push(track)
  end

  def shift
    @queue.shift
  end
end

class Album
  # Information about the album
end

class Track
  # Information about the track, including album
end

class User
  # Information about the user.
end
```



dfs monkey patch target and proc 
node class 



Class Node 
    def initialize(value)
        @value 
        @parent = nil 
        @children = [] 
    end 

    def dfs(target, &prc) 
        raise "block needed" if prc == nil 
        return self if prc.call(self) ==  target 
        
        @children.each do |child| 
         result = child.dfs(target, &prc)  #2
         result.nil? ? nil : result
        end
    
        nil   
    end
end

if prc.call(self.val, target) == 0
return self
end

self.children.each do |child|
result = child.dfs(target, &prc)
unless result.nil?
return result
end
end
nil


Class Node
    def initialize(value)
    @value = value
    @parent = nil
    @children = []
    end

    def bfs(target, &prc) 
        queue = [ self]

    until queue.empty?
        ele = queue.shift 

       if prc.call(ele, target) == 0
            return ele
        else
            ele.children.each do |child|   
             queue << child   
             end 
        end
    end


    nil
    end

end


---def bfs(&prc)
    raise "Must give a proc or target" if prc.nil?

    queue = [self]

    until queue.empty?
      visited = queue.shift
      return visited if prc.call(visited)
      queue += visited.children
    end

    nil
  end
end
