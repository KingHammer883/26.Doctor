# 26.Doctor
# -*- coding: utf-8 -*-

Created on Fri Jan 25, 2019

File: Nondirective Pyshotherapy

Program: Doctor.py
Conducts an interaction session of nondirection psychotherapy.

@author: Byen23


# Request
Write a program that emulates a nondirective psychotherapist

# Analyst

Below shows the program's interface as it changes throughout a sequence of exchanges with the user.

	Good Morning, I hope you are well today.
	What can I do for you?
	
	>> My mother and I don't get along
	Why do you say that your mother and you don't get along?
	
	>> she always favors my sister
	You seem to hink that she always favors your sister
	
	>> My dad and I get along fine
	Can you explain why your dad nad you get along fine?
	
	>> he helps me with my homework
	Please tell me more
	
	>> quit
	Have a nice day!

When the user enters a statement, the program responds in one of two ways:
	
	1. With a randomly chosen hedge, such as "Please tell me more."
	2. By changing some keyword in the user's input string and 
       appending the string to a randomly chosen qualifier.
       Thus, to "my teacher always plays favorites," the program might reply,
       "Why do you say taht your teacher always play favorites?'

# Design

The program consist of a set of collaborating functon that share a common data pool.

Two of the data sets are the hedges and the qualifiers. Because these collections do not change and their elements must be selected at random, you can use tuples to represent them. Their names, of course, are hedges and qualifiers.

The other set of data consists of mapping between first-person pronouns, and secondperson pronouns. For example, when the program sees "I" in patient's input, it should respond with a sentence containing "you". The best type of data structure to hold these correlations is a dictionary. This dictionary is named replacements.

The main function displays a greeting, displays a prompt, and waits for user input. The following is pseudocode for the main loop:
	
	output a greeting to the patient
	While True
		prompt for and input a string from the patient
		if the string equals "QUIT"
			output a sign-off message to the patient
			break
		call another function to obtain a reply to this string
		output the reply to the paitent.
		
Out therapist might not be an expert, but there is no charge for its service. What's more, our therapist seems willing to go on forever. However, if the patient must quit to do something else, he/she can do so by typing "quit" to end the program.

The reply functio expencts the patient's string as an argument and returns another string to reply. This function implements the two strategies for making replies suggested in teh analyst phase. A quarter of the time a hedge is warranted. 
Otherwise, the function constructs to reply by changing the persons in the patient's input and appending the result to a randomly selected qualifier. The reply function calls yet another function, changePerson, to perform the complex task of changing persons.
