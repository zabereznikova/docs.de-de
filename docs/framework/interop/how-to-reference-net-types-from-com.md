---
title: 'Gewusst wie: Verweisen auf .NET-Typen in COM'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f58225e41d7e09471685395dd6e2194ee5de123c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reference-net-types-from-com"></a>Gewusst wie: Verweisen auf .NET-Typen in COM
Hinsichtlich Clientcode und Servercode bestehen kaum Unterschiede zwischen COM und .NET Framework. Microsoft Visual Basic-Clients können ein .NET-Objekt im Objektkatalog anzeigen. Dort werden Objektmethoden und –syntax sowie Eigenschaften und Felder in gleicher Weise angegeben wie für ein beliebiges anderes COM-Objekt.  
  
 Der Prozess zum Importieren einer Typbibliothek ist etwas komplizierter für C++-Clients, obwohl dieselben Tools verwendet werden wie beim Exportieren von Metadaten in eine COM-Typbibliothek. Zum Verweisen auf .NET-Objektmember von einem nicht verwalteten C++-Client aus verweisen Sie auf die TLB-Datei (die mit Tlbexp.exe erstellt wurde) mit der **#import**-Anweisung. Zum Verweisen auf eine Typbibliothek von C++ müssen Sie entweder die **raw_interfaces_only**-Option angeben oder die Definitionen in die Basisklassenbibliothek Mscorlib.tlb importieren.  
  
### <a name="to-import-a-library"></a>So importieren Sie eine Bibliothek  
  
-   Geben Sie die **raw_interfaces_only**-Option in der **#import**-Anweisung an. Zum Beispiel:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     - oder -   
  
-   Schließen Sie eine #import-Direktive für Mscorlib.tlb ein. Zum Beispiel:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Registrieren von Assemblys bei COM](../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [Aufrufen eines.](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [Deploying an Application for COM Access (Bereitstellen einer Anwendung für COM-Zugriff)](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
