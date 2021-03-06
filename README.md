##### * This project is saved using Sublime Text 3, and has the Project and Workspaces files for it.

## Dictionary

__NPC__ = Non-Player Character (A bot.)<br />
__MOB__ = Monster (Usually combat NPC.)

__Text Client__ = MUD style.

__TARGET__    - A world creation. An object, like a chair, or a living object, like a cow.<br />
__WORLD__     - The actual server-side world Object(), that holds relevant world data in ready-access mode.<br />
__DB__        - The MongoDB that holds all the world data, as storage, for access by the WORLD.<br />

__USER__      - Lowest access client. Unregistered in the world, and has no saved data.<br />
__PLAYER__    - A registered USER. Saved data.<br />
__MASTER__    - A PLAYER with access to modify certain world aspects, such as TARGET details.<br />
__BUILDER__   - A MASTER with access to create and destroy world TARGETS.<br />
__GOD__       - A developer with full access rights, with abilities that are game-unrelated, such as reloading code modules.

# Node World

This Node World framework is a __virtual game world__ server that takes upon itself two important tasks:

__1.__  The server can provide access to __clients__ of all types: __Text__, __2D__, & __3D__. It handles the logic between them,
    so that each is represented properly, in front of the others.

__2.__  The server is __modular__ in its' structure, so that __modifying the world__, becomes a modular action. For example,
    an admin can add TARGETS (objects, NPCs, MOBs) to the world, but can also modify them live,
    and even toggle their AI functionality, without touching code.

Its' _general purpose_ is to redefine the framework of our virtual game worlds, so that we don't get grindy,
repetetive, story-less, intricate-less, non-modifiable game worlds. Previous games have grown from single-player
games, which were very limited. Modern games must redefine their structure, in order to accomodate
the needs of a virtual game world full of live (meat) players.

And because numerically ordered phrases speak better than thousands of lines of code,
here are more examples of the purpose of this project.

__I.__    While PLAYER functionality is simplistic (same logic as meat world),
      the modular AI lets users interact with other users, through NPC's.
      For example, a PLAYER can send another PLAYER on a quest, and guaranteeing the reward,
      by __using an NPC as an intermediary__.

__II.__   The server comes with __a default text client__, and hopefully a default 2D client, as well,
      as part of the demonstration. The text client takes from modern MUDs, only being modular
      and presented as a web-page, using Express. This makes it extremely flexible and powerful.
      NOTE: Clients only send socket 'messages', and receive finalized data. All verifications and
      logic are kept within the server.

__III.__  The WORLD uses efficiency logic, to balance out DB requests, so that they are never too many,
      but also never too big, and to balance memory usage. For example, the WORLD is split into __MAPS__,
      which are split into __ROOMS__, and MAPS (with their ROOMS) only get requested, when any USER __needs__ them.

__IV.__   The NodeJS code is split in such a way that allows a full perspective on the entire project,
      together with the __reloading of the code__, live, from the client, using GOD permissions and the
      command 'reloadcommands'. This is a developer only command. Another one is 'resetworld',
      which kicks all clients, empties the WORLD, empties the DB, and reloads the WORLD.

__V.__    While the server is meant to be flexible, it is not meant to be _wild_. It is aimed for __automacy__
      and __functionality__; not for "_everything is possible_". The requirements are specific, and
      each is defined as its' own 'system.' Each such system is loaded as a module. For example,
      the combat system is (will be) a separate module.

__VI.__   For the sake of developers, for now, all command requests by clients - which enter the command
      JS functions, are __encapsulated in a domain__, with its' own exception catcher. This works together
      with the 'reloadcommands' command.


For more information or just to chat, you can contact me at:

phuein@gmail.com

SKYPE: Phuein

FACEBOOK: Assaf Koss
