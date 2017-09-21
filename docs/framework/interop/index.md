---
title: Interoperation mit nicht verwaltetem Code
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff86b062efddde6f97555efb97247f60a6e1db98
ms.contentlocale: de-de
ms.lasthandoff: 09/18/2017

---
# <a name="interoperating-with-unmanaged-code"></a>Interoperation mit nicht verwaltetem Code
.NET Framework stuft die Interaktion mit COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten herauf. Datentypen, Methodensignaturen und Mechanismen zur Behandlung von Fehlern variieren zwischen verwalteten und nicht verwalteten Objektmodellen. Um die Interoperation zwischen .NET Framework-Komponenten und nicht verwaltetem Code sowie den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede in diesen Objektmodellen vor jeweils Clients und Servern.  
  
 Code, der unter der Kontrolle der Runtime ausgeführt wird, wird als verwalteter Code bezeichnet. Umgekehrt wird Code, der außerhalb der Runtime ausgeführt wird, wird als nicht verwalteter Code bezeichnet. Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Win32 API-Funktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Themen zur Vorgehensweise zur Zusammenarbeit mit nicht verwaltetem Code](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Enthält Links zu allen Themen zur Vorgehensweise in der Begriffsdokumentation zur Interoperabilität mit nicht verwaltetem Code.  
  
 [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Beschreibt, wie COM-Komponenten aus .NET Framework-Anwendungen verwendet werden  
  
 [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Beschreibt, wie .NET Framework-Komponenten aus COM-Anwendungen verwendet werden  
  
 [Verwenden nicht verwalteter DLL-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf  
  
 [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Bietet Tipps zum Schreiben integrierter COM-Komponenten.  
  
 [Interop-Marshalling](../../../docs/framework/interop/interop-marshaling.md)  
 Beschreibt das Marshalling für COM-Interop sowie Plattformaufruf  
  
 [Gewusst wie: Zuordnen von HRESULTs und Ausnahmen](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Beschreibt die Zuordnung zwischen Ausnahmen und HRESULTs  
  
 [Interoperation mit generischen Typen](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Beschreibt das Verhalten generischer Typen bei Verwendung in COM-Interop  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erweiterte COM-Interoperabilität](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.

