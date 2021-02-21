note: based on Lua and same languages

|Content                                             |
|----------------------------------------------------|
|[Naming](#naming)                                   |
|[Hungarian Notation](#hungarian-notation-custom)|
|[Whitespaces and Spaces](#whitespaces-and-spaces)   |
|[Others](#others)                                   |

## Naming 
- use Hungarian Notation
  ```lua
    local sUsername = "usernameX"
    local iAge      = -4
  ```

- variable names use camelCase
  ```lua
    local sVariableName = "?"
  ```
- function names use Pascal Case
  ```lua
    function PascalCase()

    end
  ```
- specify the variable env
  ```lua
    g_sGlobalVariable = "this is a global variable"
    m_sMemberVariable = "this is a member variable"
  ```

## Hungarian notation (custom)

|Name    |Hungarian Iteration|
|--------|-------------------|
|Array   | a, arr            |
|Object  | o, obj            |
|Table   | t, tbl            |
|String  | str, s            |
|Boolean | b, bl, bo         |
|Integer | i, int, n, num    |

## Whitespaces and Spaces
don't write fucking codes like stuck in your monitor, you have spacebar and enter, please use that shit

- leave space between commas
  ```lua
    -- yes
    SomeFunction(param, param1, param2)

    -- no
    SomeFunction(param,param1,param2)
    SomeFunction ( param, param1,param2 )
  ```
- leave whitespaces between not related code lines each other
  ```lua
    function Player.New(nick, teamID, weaponID)
        local self = setmetastuff()

        -- define default variables
        self.x     = 0
        self.y     = 0
        self.z     = 0
        self.score = 0

        -- define parameters
        self.nick     = nick
        self.teamID   = teamID
        self.weaponID = weaponID

    return self
    end
  ```

## Others
1. align variable defines
   ```lua
    local var         = ""
    local var2        = ""
    local var3        = ""
    local longVarName = true
   ```
2. always use brackets in statements and functions
   ```lua
    if (DEBUG) then
        Log:Error("bruh")
    end
   ```
3. use meaningful names in variable and function names
   ```lua
    function Player.New(nick, teamID, weaponID)
        -- other stuffs...

        -- ***NO
        -- define parameters
        self.nk = nick
        self.tm = team
        self.wp = weapon

        -- ***YES
        self.nick     = nick
        self.teamID   = teamID
        self.weaponID = weaponID
    end
   ```
4. leave comments to complex lines
   ```lua
   -- write player properties to chat
    for i, player in ipairs(g_arrPlayers)
    do
        for j, objPlayerProperties in pairs(player.properties)
        do
            for propertyName, value in pairs(objPlayerProperties)
            do
                if (type(value) == "table") then
                    for propertyName, value in pairs(value)
                    do
                       Chat:Write(propertyName .. " = " .. value)
                    end
                else
                    Chat:Write(propertyName .. " = " .. value)
                end
            end
        end
    end
   ```

that's it
