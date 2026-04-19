# Player Load Management & Injury Risk Dashboard

## Project Overview
This analytics project proposes a Player Load Management and Injury Risk Dashboard for an NBA organization. The tool aggregates player workload data, game usage, travel schedules, and injury history to generate a real-time availability risk score for each player. Rather than relying on subjective judgment alone, this dashboard provides objective indicators when a player's injury risk is elevated, supporting proactive decision-making.

## Decision-Making Problem
NBA teams regularly face a tradeoff between performance and player health. Playing a key player in a high-risk situation may increase the likelihood of injury, while resting them may reduce short-term competitiveness. Current decisions are often inconsistent and rely on intuition. This project addresses the need for a systematic, data-driven framework for player availability and load management decisions.

## Proposed Analytics Approach
The tool would draw on multiple data sources:
- Game log data: minutes played and workload trends  
- Schedule data: days of rest, back-to-back games, and travel  
- Injury history: player-specific patterns and recovery timelines  
- Context variables:  recent usage intensity and role  
The analysis would use a simple risk scoring approach that combines these inputs into a single risk indicator. The focus is on transparency and interpretability rather than complex modeling, allowing decision makers to understand and trust the output.

## Use by Decision Makers
Coaches would review a simple dashboard before games showing each player’s risk level. A player flagged as high risk in a back-to-back situation would trigger consideration for rest or reduced minutes. Medical staff could review the contributing factors behind each risk score. Front office executives could use longer-term patterns to support roster and contract decisions.
The interface is designed to present a clear output with minimal interpretation required, allowing decision makers to act quickly.

## Connection to Chapter 7
This idea represents the creative phase of analytics innovation. A decision-making problem has been identified, a solution has been proposed, and the required data inputs have been outlined. However, the tool has not yet been prototyped or presented to decision makers. The idea exists as a documented concept, which aligns with the role of the creative phase described in Chapter 7.

## Prototype Enhancement

**What is being changed:**
The original dashboard only looks at factors like rest days and minutes played to calculate a player's risk score. The prototype adds one more input: how physical the upcoming opponent tends to play. For example, a player facing a team known for aggressive defense with lots of fouls, hard contests and physical contact is at greater injury risk than someone facing a more passive team, even if both players had the same amount of rest. Right now the dashboard treats those two situations the same. This enhancement fixes that.

**Why this change could improve decision-making:**
Game intensity is a stronger predictor of in-game injuries than fatigue alone. A player with three days of rest going up against a team that averages 28 fouls per game and leads the league in physical contact is at higher injury risk than the rest days alone would suggest. Adding opponent defensive intensity to the risk score catches those situations before they result in missed games. Coaches get a tool that factors in what tonight's game will actually demand, not just how tired a player's legs are.
## Prototype Evaluation

**Should the prototype enhancement be integrated into the main project?**
Adding opponent defensive intensity to the risk model addresses a real gap: the baseline treats a game against the league's most physical team the same as a game against its least physical team. That is a meaningful blind spot. However, SportVU tracking data requires a licensing agreement and the scoring weights would need to be recalibrated before the new input is live. The enhancement is worth pursuing but needs those two steps completed before it replaces the current model.

**What feedback from decision makers would influence this decision?**
- Coaching staff input: Coaches who already factor in opponent physicality when making rest decisions manually would find this feature useful since it puts a number behind a judgment call they are already making.
- Team physician review: The medical staff's injury log would confirm or challenge the core assumption. If soft-tissue injuries have spiked after games against high-foul, high-contact opponents, that is direct evidence the enhancement is worth integrating.
- Data availability check: The team either has a SportVU license or it does not. If not, the annual cost needs to fit the analytics budget before the enhancement can move forward.
- Pilot testing: Running the baseline model and the enhanced model side by side for half a season and tracking how often each one correctly flagged a player who was later injured would provide the clearest evidence for or against full adoption.
