---
title: "How to: Reference .NET Types from COM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "importing type library"
  - "COM interop, referencing .NET types"
  - "interoperation with unmanaged code, referencing .NET types"
  - "referencing .NET types"
  - "interoperation with unmanaged code, importing type library"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Reference .NET Types from COM
Hinsichtlich Clientcode und Servercode bestehen kaum Unterschiede zwischen COM und .NET Framework.  Microsoft Visual Basic\-Clients können ein .NET\-Objekt im Objektkatalog anzeigen. Dort werden Objektmethoden und –syntax sowie Eigenschaften und Felder in gleicher Weise angegeben wie für ein beliebiges anderes COM\-Objekt.  
  
 Der Prozess zum Importieren einer Typbibliothek ist etwas komplizierter für C\+\+\-Clients, obwohl dieselben Tools verwendet werden wie beim Exportieren von Metadaten in eine COM\-Typbibliothek.  Zum Verweisen auf .NET\-Objektmember von einem nicht verwalteten C\+\+\-Client aus verweisen Sie auf die TLB\-Datei \(die mit Tlbexp.exe erstellt wurde\) mit der **\#import**\-Direktive.  Zum Verweisen auf eine Typbibliothek von C\+\+ müssen Sie entweder die **raw\_interfaces\_only**\-Option angeben oder die Definitionen in die Basisklassenbibliothek Mscorlib.tlb importieren.  
  
### So importieren Sie eine Bibliothek  
  
-   Geben Sie die **raw\_interfaces\_only**\-Option in der **\#import**\-Direktive an.  Beispiel:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     \- oder \-  
  
-   Schließen Sie eine \#import\-Direktive für Mscorlib.tlb ein.  Beispiel:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## Siehe auch  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/de-de/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/de-de/fb63564c-c1b9-4655-a094-a235625882ce)