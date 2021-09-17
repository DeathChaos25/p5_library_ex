# p5_library_ex
 P5 Library for TGE's atlusscriptcompiler with newly added custom functions for use with Persona 5 EX mod.  
   
   New Functions:  
     
   - void SET_HUMAN_LV( int lv ) -- Restored Game function, sets Joker's level to the specified level, range 1 -> 99
   - void SET_PERSONA_LV( int PlayerID, int targetLv, int unused ) -- Restored Game function, can only be used to raise party member levels, not lower, only updates unit stats and level, not skills (note: does not work on Joker)
   - EX_PRINTF( variable args ) -- printf implementation in flowscript
   - int GET_EQUIPPED_PERSONA( int playerID ) -- Returns the currently equipped persona ID of the specified player character, range 1 to 10  
   - int GET_ENCOUNTER_ID( void ) -- Returns the encounter ID of the current encounter the function is used on.  
   - void PERSONA_EVOLUTION2( int playerID, int personaID ) -- Enhanced game function, now allows setting a target Persona to evolve to.  
   - void AI_ACT_PERSONA_SKILL( int personaID, int battleSkillID ) -- sets target persona for enemy AI to use on certain encounters ( requires additional custom patches ) .
   - int GET_SEQ_ID( void ) -- returns the current sequence ID the game is runnning on
   - int GET_LEARNABLE_SKILL( int PartyMember, int SkillSlotID, int targetLv ) -- returns the skill ID on the given slot from a party member's PERSONA tbl entry, will return a skill ID if the skill is higher than the party member's current level but lower/same level as the target level (note: Joker excluded for obvious reasons)
   - int GET_PLAYER_LV ( int PartyMember ) -- returns a party member's current level
   - void SET_TACTICS_STATE ( int PartyMember, int TacticsState ) -- sets a party member's tactics state (Joker included) to the target value
   - void AI_SET_ENID_TARGETABLE_STATE( int enemyID, bool targetableState ) -- use from encounter script, toggles enemy's ability to be targetted by players
   - void AI_SET_TARGETABLE_STATE( bool targetableState ) -- use inside enemy BF script, toggles enemy's own ability to be targetted by players
   - void AI_ACT_SUMMON_UNITS( int EnemyID, int EnemyID, int EnemyID, int EnemyID, int customBED_subID ) -- use inside enemy BF script, summons target amount of enemies, use id 0 to not summon an enemy on selected slot, use 0 to use normal summon visual effect (note: exceeding 5 total enemies in a battle will crash the game!)


 Notes:
  - GET_LEARNABLE_SKILL gets the learnset from the actual persona tbl section of party member personas, meaning this is NOT checking the learnset stored in the save, meaning its mod compatible, if you have a custom learnset it'll just work, this also means they can learn skills if you updated the skillset in the tbl but used an existing save that has old learnset

 [Here](https://cdn.discordapp.com/attachments/681270126657798295/877766845300621322/LevelUpPlayerCharacter.c) is a useful flowscript function/macro I have made to level up party members while also obtaining any skills they should have naturally gained
 
 Exmaple of usage (within mod menu) below:  
 ![screenshot1](https://cdn.discordapp.com/attachments/681270126657798295/867081752996478976/unknown.png)  
 [Footage of said function working](https://twitter.com/DeathChaos25/status/1417484938534866953)  
 
 Just copy/paste the LevelUpPlayerCharacter macro/function at the end of your .flow file and call it like in the screenshot above.
