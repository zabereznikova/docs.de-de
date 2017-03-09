---
title: "/baseaddress (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/dllbase"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "baseaddress compiler option [C#]"
  - "/baseaddress compiler option [C#]"
  - "-baseaddress compiler option [C#]"
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# /baseaddress (C# Compiler Options)
Über die Option **\/baseaddress** können Sie die bevorzugte Basisadresse zum Laden einer DLL\-Datei angeben.  Weitere Informationen darüber, wann und warum Sie diese Option, Sie finden und [Larry Ostermans WebLog](http://go.microsoft.com/fwlink/?LinkId=107044) verwendet [Verbessern der Anwendungs\-Startzeit](http://go.microsoft.com/fwlink/?LinkId=107043).  
  
## Syntax  
  
```  
/baseaddress:address  
```  
  
## Argumente  
 `address`  
 Die Basisadresse für die DLL.  Diese Adresse kann als Dezimal\-, Hexadezimal\- oder Oktalzahl angegeben werden.  
  
## Hinweise  
 Die Standardbasisadresse für eine DLL wird von der Common Language Runtime von .NET Framework festgelegt.  
  
 Beachten Sie, dass das niederwertige Wort in dieser Adresse gerundet wird.  Wenn Sie beispielsweise 0x11110001 angeben, wird dies auf 0x11110000 gerundet.  
  
 Um den Signaturprozess für eine DLL durchzuführen, verwenden Sie die Option **–R** aus der Datei **SN.EXE**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **DLL\-Basisadresse**.  
  
     Weitere Informationen zur programmgesteuerten Festlegung dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## Siehe auch  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName>   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)