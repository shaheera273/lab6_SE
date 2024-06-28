% facts
is_a(animal, fish).
is_a(animal, bird).
is_a(bird, ostrich).
is_a(bird, canary).
is_a(bird, penguin).
is_a(penguin, opus).
is_a(canary, tweety).
is_a(bird, robin).

travel(swim, fish).
travel(fly, bird).
travel(walk, penguin).
travel(walk, ostrich).

color(white, tweety).
color(red, robin).
color(brown, penguin).
color(yellow, canary).

sound(sing, canary).
sound(sing, robin).

covering(feathers,bird).
covering(skin, animal).

%query(ID, property, value)

%rules
an_animal(X,Y) :- is_a(X, Y).
covered_by(X,Y) :- covering(X,Y).
sounds_like(X,Y) :- sound(X,Y).
color_is(X,Y) :- color(X,Y).
travel_by(X,Y) :- travel(X,Y).
