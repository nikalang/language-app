---
title: Nika Grammar
date: 2017-04-14 18:48:20
---

# § 1 Sentence

A **sentence** is a basic building block of utterance. It is either a **declarative sentence** (§ 1.1), an **imperative sentence** (§ 1.2), or an **interrogative sentence** (§ 1.3).

```
    sentence : declarative_sentence | imperative_sentence | interrogative_sentence;
```

## § 1.1 Declarative Sentence

A **declarative sentence** is a sentence that commmunicates a statement that is asserted to be true. In speech, falling intonation (lower pitch on the last syllable) is used. In writing, it ends in a full stop ("︒", vertical ideographic full stop, U+FE12). Full stops are not surrounded by spaces. Full stops ending sentences which are isolated or the last in a paragraph are omitted. A declarative sentence must contain at least one clause, then it is a simple declarative sentence. When it contains more than one clause, it is a compound declarative sentence. Clauses are joined by conjunctional particles: 고 (and), or 나 (or).

```
    declarative_sentence : clause '︒'?;
```

## § 1.2 Imperative Sentence

An **imperative sentence** is a sentence that issues a command. In speech, rising-falling intonation is used (higher pitch on the penultimate syllable, default pitch on the last). In writing, it ends in an exclamation mark ("︕", vertical ideographic exclamation mark, U+FE15). Exclamation marks are not surrounded by spaces.

```
    imperative_sentence : clause '︕';
```

## § 1.3 Interrogative Sentence

An **interrogative sentence** is a sentence that asks a question. In speech, either rising intonation (in yes-no questions; higher pitch on the last syllable) or falling intonation (other questions; lower pitch in the last syllable) is used. In writing, it ends in a question mark ("︖", vertical ideographic question mark, U+FE16). Question marks are not surrounded by spaces.

```
    interrogative_sentence : clause '︖';
```

# § 2 Clause

```
    clause : compound_clause | simple_clause;

    compound_clause : or_compound_clause | and_compound_clause;

    or_compound_clause : (clause '나')+ clause '나'?;

    and_compound_clause : (clause '고')+ clause '고'?;

    simple_clause : positive_clause | negative_clause;

    positive_clause : base_clause;

    negative_clause : base_clause '니';

    base_clause : topic? comment;

    topic : noun_phrase '하';
```

# § 3 Comment

```
    comment : compound_comment | simple_comment;

    compound_comment : or_compound_comment | and_compound_comment;

    or_compound_comment : (comment '나')+ comment '나'?;

    and_compound_comment : (comment '고')+ comment '고'?; 

    simple_comment : positive_comment | negative_comment;

    positive_comment : base_comment;

    negative_comment : base_comment '니';

    base_comment : normal_comment | adverb_emphasis_comment | object_emphasis_comment;

    normal_comment : subject? predicate;

    adverb_emphasis_comment : adverb subject predicate;

    object_emphasis_comment : object (subject | adverb) predicate;

    subject : noun_phrase '가';
```

# § 4 Predicate

```
    predicate : adverb* verb_phrase;

    adverb : noun_phrase '어';
```

# § 5 Verb Phrase

```
    verb_phrase : copular_verb_phrase | adverbial_verb_phrase | adnominal_verb_phrase |
                  descriptive_verb_phrase | action_verb_phrase;

    copular_verb_phrase : noun_phrase;

    adverbial_verb_phrase : adverb;

    adnominal_verb_phrase : adnoun;

    descriptive_verb_phrase : simple_verb | periphrastic_verb;

    action_verb_phrase : intransitive_verb_phrase | transitive_verb_phrase;

    intransitive_verb_phrase : simple_verb | periphrastic_verb;

    transitive_verb_phrase : ((bare_object | object)? simple_verb) | (object? periphrastic_verb);

    periphrastic_verb : noun_phrase '쑤루';

    object : noun_phrase '호';

    bare_object : noun_phrase;
```

# § 6 Noun Phrase 

```
    noun_phrase : compound_noun_phrase | simple_noun_phrase;

    compound_noun_phrase : or_compound_noun_phrase | and_compound_noun_phrase;

    or_compound_noun_phrase : (noun_phrase '나')+ noun_phrase '나'?;

    and_compound_noun_phrase : (noun_phrase '고')+ noun_phrase '고'?;

    simple_noun_phrase : verbal_noun | modifiable_noun;
    
    verbal_noun : declarative_verbal_noun | interrogative_verbal_noun;
    
    declarative_verbal_noun : clause '다';
    
    interrogative_verbal_noun : clause '까';

    modifiable_noun : modifiers? head;

    head : simple_noun;

    modifiers : (relative_clause | adnoun)* bare_adnoun?;

    adnoun : noun_phrase '노';

    bare_adnoun : noun_phrase;
```

# § 7 Relative Clause

```
    relative_clause : compound_relative_clause | simple_relative_clause;

    compound_relative_clause : or_compound_relative_clause | and_compound_relative_clause;

    or_compound_relative_clause : (relative_clause '나')+ relative_clause '나'?;

    and_compound_relative_clause : (relative_clause '고')+ relative_clause '고'?;

    simple_relative_clause : positive_relative_clause | negative_relative_clause;

    positive_relative_clause : base_relative_clause;

    negative_relative_clause : base_relative_clause '니';

    base_relative_clause : normal_relative_clause | adverb_emphasis_relative_clause |
                           object_emphasis_relative_clause;

    normal_relative_clause : subject? relative_predicate;

    adverb_emphasis_relative_clause : adverb subject relative_predicate;

    object_emphasis_relative_clause : object (subject | adverb) relative_predicate;
```

# § 8 Relative Predicate

```
    relative_predicate : adverb* relative_verb_phrase;
```

# § 9 Relative Verb Phrase

```
    relative_verb_phrase : descriptive_verb_phrase | action_verb_phrase;
```

