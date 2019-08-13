#Partner A 
`a ||= b`



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
