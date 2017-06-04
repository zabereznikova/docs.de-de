---
title: "How to: Generate Interop Assemblies from Type Libraries | Microsoft Docs"
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
  - "interop assemblies, generating"
  - "Type Library Importer"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Generate Interop Assemblies from Type Libraries
Mit dem Befehlszeilentool [Type Library Importer \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) können Sie Co\-Klassen und Schnittstellen, die in einer COM\-Typbibliothek enthalten sind, in Metadaten konvertieren.  Das Tool erstellt automatisch eine Interop\-Assembly und einen Namespace für die Typinformationen.  Sobald die Metadaten einer Klasse zur Verfügung stehen, können verwaltete Clients Instanzen des COM\-Typs erstellen und seine Methoden aufrufen, als würde es sich um eine .NET\-Instanz handeln.  Mit **Tlbimp.exe** können Sie vollständige Typbibliotheken sofort in Metadaten konvertieren. Es ist nicht möglich, Typinformationen für Teilmengen der in einer Typbibliothek definierten Typen zu generieren.  
  
### So generieren Sie eine Interop\-Assembly aus einer Typbibliothek  
  
1.  Verwenden Sie den folgenden Befehl:  
  
     **tlbimp** \<*Typbibliotheksdatei*\>  
  
     Wenn Sie den **\/out:**\-Schalter hinzufügen, wird eine Interopassembly mit einem veränderten Namen erstellt, z. B. LOANLib.dll.  Durch Namensveränderung lässt sich die Interopassembly leichter von der ursprünglichen COM\-DLL unterscheiden, und durch doppelt vorhandene Namen entstehende Probleme werden vermieden.  
  
## Beispiel  
 Der folgende Befehl erstellt die Loanlib.dll\-Assembly im `Loanlib`\-Namespace.  
  
```  
tlbimp Loanlib.dll  
```  
  
 Der folgende Befehl erstellt eine Interop\-Assembly mit einem veränderten Namen \(LOANLib.dll\).  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## Siehe auch  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)