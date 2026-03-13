LABORATORY #3

> Answer the following before running the simulation:
>
> 1\. What is an agent in an Agent-Based Model?

-   ​​An agent is an individual entity in the simulation that has its own
    > attributes and behavior. Agents can make decisions, interact with
    > the environment, and change over time based on rules in the model.

> 2\. What is the difference between:
>
> o global variables

-   Declared inside the global block.

-   Shared by the entire simulation.

-   All agents can access them.

-   They represent the overall environment or system state.

> o species variables?

-   Declared inside a species (like species student).

-   Each agent has its own copy of the variable.

-   The value can be different for every agent.

> 3\. What does this expression mean?
>
> student mean_of each.attention

-   This expression calculates the average attention of all student
    > agents in the simulation.

> 4\. What happens if attention continuously decreases without a break?

-   If attention keeps decreasing without breaks, the attention values
    > of students will gradually approach 0.

> **Data Observation Table**
>
> Fill in the table after 100 cycles:

+----------------------------------+-----------------------------------+
| > **Metric**                     | > **Value**                       |
+==================================+===================================+
| > Average Attention              | 0.8000000000000003                |
+----------------------------------+-----------------------------------+
| > Average Performance            | 1.0                               |
+----------------------------------+-----------------------------------+
| > High Attention Count           | 25                                |
+----------------------------------+-----------------------------------+
| > Number of Breaks Occurred      | 2                                 |
+----------------------------------+-----------------------------------+

**Guided Code Analysis**

**Activity 1: Break Frequency**

> Original code:
>
> if (cycle mod 30 = 0)
>
> **Task:**
>
> Change break interval to:
>
> 15 cycles
>
> **Questions:**
>
> 1\. Does attention increase faster?

-   Yes. Attention increases faster because breaks occur more often.
    > Each break allows students to recover attention by adding 0.05 to
    > their attention level.

> 2\. Does performance grow faster?

-   Yes, performance tends to grow faster. In the model, performance
    > increases when attention is greater than 0.6, this triggers the
    > performance increase more frequently, which causes average
    > performance to grow faster.

> 3\. Is the system more stable?

-   Yes, the system becomes more stable. Frequent breaks prevent
    > attention from dropping too low.

**Activity 2: Attention Decay Rate**

> Original:
>
> attention \<- max(0.0, attention - 0.02);
>
> **Task:**
>
> Change decay rate to:
>
> 0.05
>
> **Observe:**
>
> • Does attention collapse?

-   Yes. The average attention becomes much lower compared to the
    > original model. Since attention now decreases by 0.05 each cycle,
    > students lose focus much faster than before.

> • Does performance still improve?
>
> Explain Why?

-   Performance improves much more slowly, and in many cases it may stop
    > improving. This happens because performance only increases when
    > attention is greater than 0.6. With the faster decay rate,
    > students rarely maintain attention above this threshold.

> **Activity 3: Performance Growth Condition**
>
> Original:
>
> if (attention \> 0.6)
>
> **Task:**
>
> Change threshold to:
>
> 0.8
>
> **Questions:**
>
> • Does performance improve slower?

-   Yes, performance improves slower. When the threshold is 0.8, fewer
    > students reach the level of attention required for performance
    > growth. In the model, attention often fluctuates due to movement,
    > decay during class time, and recovery during breaks. Because the
    > required attention level is higher, the condition that increases
    > performance is triggered less often.

> • What does this represent in real classroom settings?

-   This represents a classroom environment where very high focus is
    > required before learning outcomes improve. In real classrooms,
    > some tasks or subjects require strong concentration before
    > students can understand the material.

> **Experiment: Class Size Impact (30 minutes)**
>
> Use parameter:
>
> Initial number of students
>
> Test:

+-----------+----------------------+-----------------------------------+
| > **Students**    | > **Avg Attention**  | > **Avg Performance**     |
|                   |                      |                           |
+===========+======================+===================================+
| > 10      | 0.7395190570783238   | 0.673                             |
+-----------+----------------------+-----------------------------------+
| > 25      | 0.7264000000000003   | 0.708574555113872                 |
+-----------+----------------------+-----------------------------------+
| > 60      | 0.7364000000000003   | 0.8104210354514594                |
+-----------+----------------------+-----------------------------------+
| > 100     | 0.8092954259761629   | 0.7340000000000003                |
+-----------+----------------------+-----------------------------------+

**Analysis Questions:**

> 1\. Does increasing class size affect average attention?

-   Class size alone does not strongly control attention. Instead,
    > attention is mostly affected by the break cycles and attention
    > decay rules defined in the student behavior.

> 2\. Does mobility create more randomness?

-   Yes, As the number of students increases, more agents are moving
    > randomly in the environment.

> 3\. Is emergent behavior visible?

-   Yes, emergent behavior is visible in the simulation. These patterns
    > appear from the interaction of many students, not from a single
    > rule controlling the whole class.

> **Data Analysis Task (Optional Python)**
>
> Using Excel or Power Query Editor
>
> 1\. Load classroom_data.csv
>
> 2\. Plot:
>
> o Attention vs Cycle
>
> o Performance vs Cycle
>
> 3\. Identify break cycles.

-   0, 15, 30, 45, 60, 75, 90

> 4\. Compute correlation between attention and performance.

-   The computed correlation is -0.2467. This indicates a weak negative
    > relationship between attention and performance in the dataset.

> **Question:**
>
> Is performance strongly dependent on attention?

-   No, performance is not strongly dependent on attention in this
    > result. The correlation value -0.2467 indicates a weak
    > relationship between the two variables.

**Critical Thinking Questions**

> 1\. Why does performance only increase when attention \> 0.6?

-   Performance only increases when attention is greater than 0.6
    > because the model assumes that students need a minimum level of
    > focus before learning can improve.

> 2\. Is this model deterministic or stochastic?

-   The model is stochastic because it includes elements of randomness.
    > For example, the students initial attention, mobility, and
    > movement direction are generated using random values. Because of
    > this, running the simulation multiple times may produce slightly
    > different results.

> 3\. What real-world classroom factors are missing?

-   The model does not include several real classroom factors such as
    > teacher influence, student ability differences, and peer
    > interaction. It also ignores classroom distractions, lesson
    > difficulty, and student motivation. Including these factors could
    > make the simulation more realistic.

> 4\. How would peer influence affect the system?

-   Peer influence could change how attention and performance develop in
    > the classroom. Students might increase their attention if they are
    > surrounded by focused classmates, or lose focus if others around
    > them are distracted. This could create groups of high-performing
    > or low-performing students in the simulation.

4
