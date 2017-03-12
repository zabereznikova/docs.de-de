---
title: "/debug (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/debug"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "debug compiler option [C#]"
  - "-debug compiler option [C#]"
  - "/debug compiler option [C#]"
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# /debug (C# Compiler Options)
Die Option **\/debug** bewirkt, dass der Compiler Debuginformationen generiert und in die Ausgabedatei\(en\) einfügt.  
  
## Syntax  
  
```  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## Argumente  
 `+` &#124; `-`  
 Wenn Sie `+` oder nur **\/debug** angeben, generiert der Compiler Debuginformationen und platziert diese in einer Programmdatenbank \(PDB\-Datei\).  Wenn Sie `-` angeben, das wirksam ist, wenn Sie **\/debug** nicht angeben, werden keine Debuginformationen erstellt.  
  
 `full` &#124; `pdbonly`  
 Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden.  Das vollständige Argument, das wirksam ist, wenn Sie **\/debug:pdbonly** nicht angeben, ermöglicht das Anfügen eines Debuggers an das laufende Programm.  Durch Angeben von **pdbonly** wird das Debuggen von Quellcode ermöglicht, wenn das Programm im Debugger gestartet wird. Der Assembler wird jedoch nur angezeigt, wenn das laufende Programm an den Debugger angefügt ist.  
  
## Hinweise  
 Verwenden Sie diese Option zum Erstellen von Debugbuilds.  Wenn **\/debug**, **\/debug\+** oder **\/debug:full** nicht angegeben sind, können Sie die Ausgabedatei des Programms nicht debuggen.  
  
 Beachten Sie bei Verwendung von **\/debug:full**, dass **\/debug:full** größere Auswirkungen auf die Geschwindigkeit und Größe des JIT\-optimierten Codes und geringe Auswirkungen auf die Qualität des Codes hat.  Sie sollten **\/debug:pdbonly** oder keine PDB für das Generieren von Versionscode verwenden.  
  
> [!NOTE]
>  Ein Unterschied zwischen **\/debug:pdbonly** und **\/debug:full** besteht darin, dass der Compiler bei Verwendung von **\/debug:full** ein <xref:System.Diagnostics.DebuggableAttribute> ausgibt, anhand dessen dem JIT\-Compiler mitgeteilt wird, dass Debuginformationen verfügbar sind.  Deshalb erhalten Sie bei Verwendung von **\/debug:full** eine Fehlermeldung, wenn der Code das auf den Wert false festgelegte <xref:System.Diagnostics.DebuggableAttribute> enthält.  
  
 Weitere Informationen zum Konfigurieren der Debugleistung einer Anwendung finden Sie unter [Erleichtern des Debuggens für ein Abbild](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
 Informationen zum Ändern des Speicherorts der PDB\-Datei finden Sie unter [\/pdb \(Specify Debug Symbol File\)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Debuginfo**.  
  
 Informationen über das programmgesteuerte Festlegen der Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## Beispiel  
 In diesem Beispiel werden Debuginformationen in die Ausgabedatei `app.pdb` eingefügt:  
  
```  
csc /debug /pdb:app.pdb test.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)