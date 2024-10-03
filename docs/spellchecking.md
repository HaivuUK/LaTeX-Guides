# Spellchecking

Spellchecking is generally dependent on the editor you are using. Most editors have built-in spellchecking, but if 
you are using a simple text editor, you can use a spellchecker like `aspell` or `hunspell`. 

With more feature-rich editors like TeXstudio and Visual Studio Code, you can full grammar checking and spellchecking
as you type using the LanguageTool extension.

Information for how to do this in Visual Studio Code can be found [here](https://valentjn.github.io/ltex/).

For TeXstudio:

Note You need TeXstudio 2.12.2 or later to work with LT 3.6 or later

You need have the standalone LanguageTool java application installed on your system. You can download it from
[here](https://languagetool.org/).

In TeXstudio navigate to Options > Configure TexStudio… > Language Checking > LanguageTool (near the bottom as of 4.8.4).

You should start the LanguageTool stand-alone version, languagetool.jar. Then simply open Options and select the 
option to run it as HTTP server. By default, it uses port 8081. You can change this in the options. But you need to 
change this in TeXstudio as well.

If TexStudio is configured to use inline grammar checking (which is the default, see Options > Configure TexStudio… > 
Editor > Inline Checking > Grammar), you should see grammar checks immediately.

Occasionally it will flag LaTeX commands as errors.
