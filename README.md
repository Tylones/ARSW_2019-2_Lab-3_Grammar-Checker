# ARSW_2019-2_Lab-3_Grammar-Checker

## Part I - Basic workshop

### 1)

*nothing to say*

### 2)

The line indicating to automatically search in the package is : 

```
  <context:component-scan base-package="edu.eci.arsw" />
```

### 3)

* 1 : To make GrammarChecker a bean depending on a spell checker, we have to add *@Service* before the class, and *@Autowired* before the SpellChecker attribute :
```
  @Service
  public class GrammarChecker {

      @Autowired
      SpellChecker sc;

      String x;
      
      /*
        functions
      */
      
  }
```

* 2 : To make the GrammarChecker only using an EnglishSpellChecker, we have to put *@Service* before the class, but not before the SpanishSpellChecker class : 
```
@Service
public class EnglishSpellChecker implements SpellChecker {

	@Override
	public String checkSpell(String text) {		
		return "Checked with english checker:"+text;
	}

        
}
```

### 4) 

By executing the program with what we added previously, the program outputs : 

*Spell checking output:Checked with english checker:la la la Plagiarism checking output: Not available yet*


## Part II

To use the SpanishSpellChecker instead of the EnglishSpellChecker, we just have to remove the *@Service* before the EnglishSpellChecker class, and add it before the SpanishSpellChecker class.

Executing the program after doing such changes outputs :

*Spell checking output:revisando (la la la ) con el verificador de sintaxis del espanolPlagiarism checking output: Not available yet*
