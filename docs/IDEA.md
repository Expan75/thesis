# Idea

Automated knowledge graph construction via finetuned LLMs for intelligent automotive agents

### Goal

Construct small knowledge graphs based on user input.

1. Wakeword detection (Hi Zeekr!)
2. Transcribe (whisper or something else)
3. Parse NLP into triplets
4. Parse knowledge graph
5. Normalize and merge the graph with past representations
6. RAG the full graph for query estimation and delegation to other services.

### Concrete scenarios

1. Intelligent iternary chaining

   Trip chaining:

   U: Hi Zeekr! I need to make a stop for groceries home from work.
   Z: Okay! Should I add <grocery store> to the iternary?
   U: Yes, please!
   Z: Added <grocery store> to the iternary.

   U: Oh I almost forgot, I need to pick up <child> on the way. (noticy lack of wakeword if within cooldown)
   Z: Sure! Where from? <--query completion
   U: <school>
   Z: Added <school> to iternary store

2. Significant entities

   Prior conversations should accrue a knowledge graph of significant entities,
   primarily focused on places and people (associated to places). Support CRUDable aliases,
   e.g. "Zeekr, take me home" - "Sure Dave! Where is home?" - "<address>" or "Zeekr, I need to pick up <name> from the airport"
