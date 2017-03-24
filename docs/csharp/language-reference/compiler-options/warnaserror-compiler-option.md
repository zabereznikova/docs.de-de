---
title: "/warnaserror (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warnaserror"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/warnaserror compiler option [C#]"
  - "-warnaserror compiler option [C#]"
  - "warnaserror compiler option [C#]"
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /warnaserror (C# Compiler Options)
Die Option **\/warnaserror\+** behandelt alle Warnungen als Fehler.  
  
## Syntax  
  
```  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## Hinweise  
 Alle Meldungen, die normalerweise als Warnungen angezeigt werden, werden als Fehler gemeldet, und der Buildprozess wird angehalten. \(Es werden keine Ausgabedateien generiert.\)  
  
 Standardmäßig ist **\/warnaserror\-** aktiviert. Das heißt, dass die Generierung einer Ausgabedatei durch Warnungen nicht verhindert wird.  Durch **\/warnaserror** \(entspricht **\/warnaserror\+**\) werden Warnungen als Fehler behandelt.  
  
 Alternativ dazu können auch nur einige ausgewählte Warnungen als Fehler behandelt werden. Erstellen Sie dazu eine Liste von durch Trennzeichen getrennten Warnungsnummern, die als Fehler behandelt werden sollen.  
  
 Verwenden Sie [\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md), um die Warnstufen anzugeben, die der Compiler anzeigen soll.  Mithilfe von [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) können Sie bestimmte Warnungen deaktivieren.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Warnungen als Fehler behandeln**.  
  
     Weitere Informationen zur programmgesteuerten Festlegung dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert, wobei der Compiler keine Warnungen anzeigt:  
  
```  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)