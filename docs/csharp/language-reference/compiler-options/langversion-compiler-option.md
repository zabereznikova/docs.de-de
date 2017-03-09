---
title: "/langversion (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/langversion"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/langversion compiler option [C#]"
  - "-langversion compiler option [C#]"
  - "langversion compiler option [C#]"
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# /langversion (C# Compiler Options)
Bewirkt, dass der Compiler nur Syntax akzeptiert, die in der gewählten C\#\-Sprachspezifikation eingeschlossen ist.  
  
## Syntax  
  
```  
/langversion:option  
```  
  
## Argumente  
 `option`  
 Folgende Werte sind gültig:  
  
|Option|Bedeutung|  
|------------|---------------|  
|default|Der Compiler akzeptiert sämtliche gültige Sprachsyntax.|  
|ISO\-1|Der Compiler akzeptiert nur Syntax, die der C\#\-Sprachspezifikation 23270:2003 gemäß ISO\/IEC entspricht.|  
|ISO\-2|Der Compiler akzeptiert nur Syntax, die der C\#\-Sprachspezifikation 23270:2006 gemäß ISO\/IEC entspricht.  Diese Spezifikation ist auf der Website [ISO](http://go.microsoft.com/fwlink/?LinkId=144406) verfügbar.|  
|3|Der Compiler akzeptiert nur Syntax, die in der Version 3.0 von [C\#\-Sprachspezifikation](../../../csharp/language-reference/language-specification.md) enthalten ist.|  
  
## Hinweise  
 Metadaten, auf die von der C\#\-Anwendung verwiesen wird, sind nicht der **\/langversion**\-Compileroption unterworfen.  
  
 Da alle Versionen des C\#\-Compilers Erweiterungen der Sprachspezifikation enthalten, bietet **\/langversion** nicht die entsprechenden Funktionen einer früheren Version des Compilers.  
  
 Unabhängig von der verwendeten **\/langversion**\-Einstellung verwenden Sie zum Erstellen von EXE\- oder DLL\-Dateien die aktuelle Version der Common Language Runtime.  Ausnahmen stellen friend\-Assemblys und [\/moduleassemblyname \(Specify Friend Assembly for Module\)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) dar, die unter **\/langversion:ISO\-1** funktionieren.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Sprachversion**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\#\-Sprachspezifikation](../../../csharp/language-reference/language-specification.md)