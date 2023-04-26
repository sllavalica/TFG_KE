# TFG_KE

El documento de data es para ver aspectos descriptivos de los datos.

El código de keybert_code está actualizado con los cambios hablados el martes, el código de yake_code NO.

Para hacer la lista de combinaciones posibles descritas en el paper (Following Justeson and Katz (1995) these patterns are adjective-noun; 
noun-noun; adjective-adjective-noun; adjective noun-noun; noun-adjective-noun; noun-noun-noun; and noun-preposition-noun.), se pueden obtener con el siguiente código:


adjectives = ['JJ', 'JJR', 'JJS']
nouns = ['NN', 'NNS', 'NNP', 'NNPS']
prepositions = ['IN']

patterns = []

# adjective-noun
patterns.extend([(adj, noun) for adj in adjectives for noun in nouns])

# noun-noun
patterns.extend([(noun1, noun2) for noun1 in nouns for noun2 in nouns])

# adjective-adjective-noun
patterns.extend([(adj1, adj2, noun) for adj1 in adjectives for adj2 in adjectives for noun in nouns])

# adjective-noun-noun
patterns.extend([(adj, noun1, noun2) for adj in adjectives for noun1 in nouns for noun2 in nouns])

# noun-adjective-noun
patterns.extend([(noun1, adj, noun2) for noun1 in nouns for adj in adjectives for noun2 in nouns])

# noun-noun-noun
patterns.extend([(noun1, noun2, noun3) for noun1 in nouns for noun2 in nouns for noun3 in nouns])

# noun-preposition-noun
patterns.extend([(noun1, prep, noun2) for noun1 in nouns for prep in prepositions for noun2 in nouns])

# imprimir todas las combinaciones posibles
print(patterns)

print(len(patterns))
