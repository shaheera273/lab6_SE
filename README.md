:- use_module(library(lists)). % for member/2
% frame(ID, Slots).
frame( car,
	[ comment-'A vehicle used for transport'
	]
).
frame( lancer,
	[ ako-car
	, manufacturer-mitsubishi
	, top_speed-127
	, mpg-17
	]
).
frame( sierra,
	[ ako-car
	, manufacturer-ford
	, top_speed-118
	, mpg-23
	]
).
frame( 'VIN_JM1BK313141132051',
	[ isa-sierra
	, mot-invalid
	, colour-silver
	]
).

% rules
query(ID, Slot, Value) :-
	frame(ID, Slots),
	member(Slot-Value, Slots).
query(ID, Slot, Value) :-
	frame(ID, Slots),
	member(isa-Class, Slots),
	query(Class, Slot, Value).
query(ID, Slot, Value) :-
	frame(ID, Slots),
	member(ako-Parent, Slots),
	query(Parent, Slot, Value).
