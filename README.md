# p5_library_ex
 P5 Library for TGE's atlusscriptcompiler with stubbed functions replaced with custom ones for use with expanded flowscript functions patch.  
   
   New Functions:  
     
   - void SET_HUMAN_LV( int lv ) -- Restored Game function, sets Joker's level to the specified level, range 1 -> 99
   - int GET_EQUIPPED_PERSONA( int playerID ) -- Returns the currently equipped persona ID of the specified player character, range 1 -> 10  
   - int GET_ENCOUNTER_ID( void ) -- Returns the encounter ID of the current encounter the function is used on.  
   - void PERSONA_EVOLUTION( int playerID, int personaID ) -- Enhanced game function, now allows setting a target Persona to evolve to.  
   - void AI_ACT_PERSONA_SKILL( int personaID, int battleSkillID ) -- sets target persona for enemy AI to use on certain encounters ( requires additional custom patches ) .  
