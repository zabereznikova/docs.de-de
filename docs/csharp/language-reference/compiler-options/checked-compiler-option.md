---
title: "/checked (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked compiler option [C#]"
  - "-checked compiler option [C#]"
  - "/checked compiler option [C#]"
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# /checked (C# Compiler Options)
Die Option **\/checked** gibt an, ob eine Ganzzahlarithmetikanweisung, die zu einem Wert führt, der nicht im Bereich des Datentyps ist und der nicht im Gültigkeitsbereich eines [checked](../../../csharp/language-reference/keywords/checked.md)\-Schlüsselworts bzw. [unchecked](../../../csharp/language-reference/keywords/unchecked.md)\-Schlüsselworts ist, eine Laufzeitausnahme auslöst.  
  
## Syntax  
  
```  
/checked[+ | -]  
```  
  
## Hinweise  
 Eine Ganzzahlarithmetikanweisung, die sich im Gültigkeitsbereich der Schlüsselwörter `checked` oder `unchecked` befindet, wird durch die Option **\/checked** nicht beeinflusst.  
  
 Ergibt eine Ganzzahlarithmetikanweisung, die sich nicht im Gültigkeitsbereich der Schlüsselwörter `checked` oder `unchecked` befindet, einen Wert außerhalb des Datentypbereichs, und wird bei der Kompilierung **\/checked\+** \(**\/checked**\) verwendet, generiert diese Anweisung eine Ausnahme zur Laufzeit.  Wenn **\/checked\-** bei der Kompilierung verwendet wird, verursacht diese Anweisung keine Ausnahme zur Laufzeit.  
  
 Der Standardwert für diese Option ist **\/checked\-**.  Ein Szenario für die Verwendung von **\/checked\-** ist, wenn große Anwendungen erstellt werden.  Manchmal werden automatisierte Tools verwendet, um solche Anwendungen zu erstellen, und solch ein Tool legt möglicherweise automatisch **\/checked** auf \+ fest.  Sie können den globalen Standard des Tools überschreiben, indem Sie **\/checked\-** angeben.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  Weitere Informationen finden Sie unter [Seite "Erstellen", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Auf arithmetischen Über\-\/Unterlauf überprüfen**.  
  
 Weitere Informationen zum programmgesteuerten Zugriff auf diese Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## Beispiel  
 Der folgende Befehl kompiliert `t2.cs`.  Die Verwendung von `/checked` im Befehl gibt an, dass jede ganzzahlige arithmetische Anweisung in der Datei, die nicht im Bereich eines `checked`\- oder `unchecked`\-Schlüsselworts ist, und die einen Wert ergibt, der außerhalb des Bereichs des Datentyps ist, zur Laufzeit eine Ausnahme auslöst.  
  
```  
csc t2.cs /checked  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7)