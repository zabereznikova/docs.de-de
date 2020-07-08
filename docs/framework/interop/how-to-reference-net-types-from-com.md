---
title: 'Vorgehensweise: Verweisen auf .NET-Typen in COM'
description: Verweisen Sie auf .NET-Typen in COM. VB-Clients können ein .NET-Objekt im Objektbrowser anzeigen. C++-Clients müssen hingegen mit der Importanweisung \# auf eine TLB-Datei verweisen.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: f8d052c7b9bac9c4bab61ab1950e9e89a7c73912
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618960"
---
# <a name="how-to-reference-net-types-from-com"></a>Vorgehensweise: Verweisen auf .NET-Typen in COM
Hinsichtlich Clientcode und Servercode bestehen kaum Unterschiede zwischen COM und .NET Framework. Microsoft Visual Basic-Clients können ein .NET-Objekt im Objektkatalog anzeigen. Dort werden Objektmethoden und –syntax sowie Eigenschaften und Felder in gleicher Weise angegeben wie für ein beliebiges anderes COM-Objekt.  
  
 Der Prozess zum Importieren einer Typbibliothek ist etwas komplizierter für C++-Clients, obwohl dieselben Tools verwendet werden wie beim Exportieren von Metadaten in eine COM-Typbibliothek. Zum Verweisen auf .NET-Objektmember von einem nicht verwalteten C++-Client aus verweisen Sie auf die TLB-Datei (die mit Tlbexp.exe erstellt wurde) mit der **#import**-Anweisung. Zum Verweisen auf eine Typbibliothek von C++ müssen Sie entweder die **raw_interfaces_only**-Option angeben oder die Definitionen in die Basisklassenbibliothek Mscorlib.tlb importieren.  
  
### <a name="to-import-a-library"></a>So importieren Sie eine Bibliothek  
  
- Geben Sie die **raw_interfaces_only**-Option in der **#import**-Anweisung an. Zum Beispiel:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     - oder -  
  
- Schließen Sie eine #import-Anweisung für Mscorlib.tlb ein. Zum Beispiel:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von .NET Framework-Komponenten in COM](exposing-dotnet-components-to-com.md)
- [Registrieren von Assemblys bei COM](registering-assemblies-with-com.md)
- [Aufrufen eines .NET-Objekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Deploying an Application for COM Access (Bereitstellen einer Anwendung für COM-Zugriff)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
