all: BNFC_Util.ml
	ocamlyacc ParLambda.mly
	ocamllex LexLambda.mll
	ocamlc -o TestLambda BNFC_Util.ml AbsLambda.ml SkelLambda.ml ShowLambda.ml PrintLambda.ml ParLambda.mli ParLambda.ml LexLambda.ml TestLambda.ml

BNFC_Util.ml: Lambda.cf
	bnfc -ocaml $<
	touch $@

clean:
	-rm -f *.cmi *.cmo *.o

distclean: clean
	-rm -f LexLambda.* ParLambda.* LayoutLambda.* SkelLambda.* PrintLambda.* ShowLambda.* TestLambda.* AbsLambda.* TestLambda BNFC_Util.ml *.bak SkelProgram.ml

test:
	./TestLambda ../example/ex01.program
	@echo "------------------------------------------------------------"
	./TestLambda ../example/ex02.program
	# ./TestLambda ../example/ex03.program
