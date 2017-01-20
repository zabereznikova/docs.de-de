---
title: "/warn (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/warn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "warning level [C#]"
  - "/w compiler option [C#]"
  - "-w compiler option [C#]"
  - "-warn compiler option [C#]"
  - "/warn compiler option [C#]"
  - "w compiler option [C#]"
  - "warn compiler option [C#]"
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /warn (C# Compiler Options)
Die Option **\/warn** gibt die vom Compiler anzuzeigende Warnstufe an.  
  
## Syntax  
  
```  
/warn:option  
```  
  
## Argumente  
 `option`  
 Die Warnstufe, die bei der Kompilierung angezeigt werden soll. Bei niedrigen Werten werden nur Warnungen mit hohem Schweregrad angezeigt; bei höheren Werten werden mehr Warnungen angezeigt.  Gültige Werte liegen zwischen 0 und 4:  
  
|Warnstufe|Bedeutung|  
|---------------|---------------|  
|0|Schaltet die Ausgabe aller Warnungen aus.|  
|1|Zeigt schwerwiegende Warnungen an.|  
|2|Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an \(z. B. zu ausgeblendeten Klassenmembern\).|  
|3|Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z. B. Warnungen zu Ausdrücken, die immer den Wert `true` oder `false` ergeben.|  
|4 \(Standard\)|Zeigt alle Warnungen der Stufe 3 sowie Informationswarnungen an.|  
  
## Hinweise  
 Informationen zu einem Fehler oder zu einer Warnung finden Sie unter dem entsprechenden Fehlercode im Hilfeindex.  Weitere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung zu erhalten finden Sie unter [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).  
  
 Mit [\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) können Sie alle Warnungen als Fehler behandeln.  Mithilfe von [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) können Sie bestimmte Warnungen deaktivieren.  
  
 **\/w** ist die Kurzform von **\/warn**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Warnstufe**.  
  
 Informationen darüber, wie Sie diese Compileroption programmgesteuert festlegen können, finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert, wobei der Compiler nur Warnungen der Stufe 1 anzeigen soll:  
  
```  
csc /warn:1 in.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)