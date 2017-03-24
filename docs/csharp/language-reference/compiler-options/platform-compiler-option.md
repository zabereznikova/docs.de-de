---
title: "/platform (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/platform"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "platform compiler option [C#]"
  - "-platform compiler option [C#]"
  - "/platform compiler option [C#]"
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 46
---
# /platform (C# Compiler Options)
Gibt an, welche Version der Common Language Runtime \(CLR\) die Assembly ausführen kann.  
  
## Syntax  
  
```  
/platform:string  
```  
  
#### Parameter  
 `string`  
 anycpu \(Standard\), anycpu32bitpreferred, ARM, x86, x64 oder Itanium.  
  
## Hinweise  
  
-   **anycpu** \(Standard\) kompiliert die Assembly, auf jede beliebige Plattform ausgeführt werden.  Die Anwendung ist als 64\-Bit\-Prozess, wann immer möglich ausgeführt und schlägt zurück in 32\-Bit, wenn nur dieser Modus verfügbar ist.  
  
-   **anycpu32bitpreferred** kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.  Die Anwendung wird im 32\-Bit\-Modus auf Systemen, mit 64\-Bit und 32\-Bit\-Anwendungen unterstützen.  Sie können diese Option nur für Projekte angeben, die auf .NET Framework 4.5 abzielen.  
  
-   **ARM** kompiliert die Assembly, auf einem Computer ausgeführt werden, der einen auf RISC\-Computer \(arm\)\- Prozessor besitzt.  
  
-   **x64** kompiliert die von der 64\-Bit\-CommonLanguage Runtime auf einem Computer ausgeführt werden Assembly, der EM64T\-Anweisung AMD64\- oder unterstützt.  
  
-   **x86** kompiliert die vom 32\-Bit\-Prozess, x86\-compatible Common Language Runtime ausgeführt werden, Assembly.  
  
-   **Itanium** kompiliert die von der 64\-Bit\-CommonLanguage Runtime auf einem Computer mit einem Itanium\-Prozessor auszuführende Assembly.  
  
 Unter einem 64\-Bit\-Windows\-Betriebssystem:  
  
-   Assemblys, die mit **\/platform:x86** kompiliert werden, werden auf dem Ausführen des 32\-Bits CLR unter WOW64 aus.  
  
-   Eine DLL, die mit **\/platform:anycpu** kompiliert wird, wird auf demselben CLR aus, das der Prozess, in die sie geladen wird.  
  
-   Ausführbare Dateien, die mit **\/platform:anycpu** kompiliert werden, werden auf dem von der 64\-Bit\-CLR aus.  
  
-   Die ausführbaren Dateien, die mit **\/platform:anycpu32bitpreferred** kompiliert werden, werden auf dem unter CLR aus.  
  
 Das Festlegen **anycpu32bitpreferred** ist nur für ausführbare Dateien \(.EXE\) zulässig, und sie ist .NET Framework 4.5.  
  
 Weitere Informationen über das Entwickeln einer Anwendung für die Ausführung unter einem 64\-Bit\-Windows\-Betriebssystem finden Sie unter [64\-Bit\-Anwendungen](../Topic/64-bit%20Applications.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Zielplattform** und, für Projekte, die auf .NET Framework 4.5 abzielen, das Kontrollkästchen **32\-Bit bevorzugen** löschen.  
  
 **Hinweis**  
 **\/platform** ist in der Entwicklungsumgebung von Visual C\# Express nicht verfügbar.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie die **\/platform** \- Option verwendet, um anzugeben, dass die Anwendung durch die 64\-Bit\-Version der CLR auf einem 64\-Bit\-Windows\-Betriebssystem ausgeführt werden soll.  
  
```  
csc /platform:anycpu filename.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)