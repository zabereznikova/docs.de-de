---
title: "/bugreport (C# Compiler Options) | Microsoft Docs"
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
  - "/bugreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/bugreport compiler option [C#]"
  - "-bugreport compiler option [C#]"
  - "bugreport compiler option [C#]"
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /bugreport (C# Compiler Options)
Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.  
  
## Syntax  
  
```  
/bugreport:file  
```  
  
## Argumente  
 `file`  
 der Name der Datei, die den Problembericht enthalten soll.  
  
## Hinweise  
 Die **\/bugreport**\-Option gibt an, dass die folgenden Informationen in `file` eingefügt werden sollen:  
  
-   Eine Kopie aller bei der Kompilierung verwendeten Quellcodedateien.  
  
-   Eine Liste der bei der Kompilierung verwendeten Compileroptionen.  
  
-   Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.  
  
-   Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET Framework und SDK enthaltene Assemblys.  
  
-   Compilerausgabe, falls vorhanden.  
  
-   Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
-   Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
 Wenn diese Option mit **\/errorreport:prompt** oder **\/errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.  
  
 Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
 Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/errorreport \(Set Error Reporting Behavior\)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)