# Matchday – Requirements

Version: 0.1
Date: 2026-11-27

## 1. Purpose
Matchday is a web application for managing amateur football leagues and clubs.
Coaches plan match days, players report their availability, referees submit
match reports, and the system calculates league tables, player statistics and
season outcome probabilities (via Monte Carlo simulation).

## 2. Roles
| Role | Description |
|---|---|
| Admin | Manages leagues, seasons, clubs, referees and user roles |
| Coach | Manages a team's squad and match-day planning |
| Player | Member of a team; responds to upcoming matches |
| Referee | Officiates assigned matches and submits match reports |
| Guest | Not logged in; views public league information |

## 3. User stories

### Admin
- **A1** As an admin, I want to create a season with a list of teams and
  generate the fixtures automatically, so that I don't have to plan every
  matchday by hand.
  - Every team plays every other team twice (home and away)
  - No team plays more than once per matchday
  - With an odd number of teams, one team has a bye each matchday
- **A2** As an admin, I want to assign a referee to a match, so that it is
  clear who officiates and who may submit the report.
  - A referee cannot be assigned to two matches at the same time
- **A3** As an admin, I want to correct a submitted match result, so that
  mistakes in reports can be fixed.
  - Every correction is logged (who, when, old value, new value)
  - Table and statistics are recalculated after a correction
- **A4** As an admin, I want to assign roles to users, so that people only
  get the permissions they need.

### Coach
- **C1** As a coach, I want to see which players are available for the next
  match, so that I can plan my line-up.
  - Shows available / unavailable / no response for every squad player
- **C2** As a coach, I want to add and remove players from my squad, so that
  the squad reflects the real team.
  - A player belongs to at most one team per season
- **C3** As a coach, I want to see player statistics (appearances, goals,
  yellow and red cards), so that I can make informed decisions.

### Player
- **P1** As a player, I want to mark myself as available or unavailable for a
  match, so that my coach can plan.
  - Can be changed until kickoff
  - Optional short reason (e.g. "work", "injured")
- **P2** As a player, I want to see my team's upcoming fixtures,