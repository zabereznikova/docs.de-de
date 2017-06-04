---
title: "Interoperating with Unmanaged Code | Microsoft Docs"
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
  - "unmanaged code, interoperation"
  - "managed code, interoperation with unmanaged code"
  - ".NET Framework, interoperation with unmanaged code"
  - "unmanaged code"
  - "interoperation with unmanaged code"
  - "interoperation with unmanaged code, about interoperation"
  - "components [.NET Framework], interoperation with unmanaged code"
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Interoperating with Unmanaged Code
Das .NET Framework fördert die Interaktion mit COM\-Komponenten, COM\+\-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten.  Datentypen, Methodensignaturen und Fehlerbehandlungsroutinen sind in verwalteten und nicht verwalteten Objektmodellen unterschiedlich.  Um die Interoperation zwischen den .NET Framework\-Komponenten und nicht verwaltetem Code zu erleichtern und den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede zwischen diesen Objektmodellen vor Clients und Servern.  
  
 Unter der Kontrolle der Common Language Runtime ausgeführter Code wird als verwalteter Code bezeichnet,  außerhalb dieser Kontrolle ausgeführter entsprechend als nicht verwalteter Code.  Um nicht verwalteten Code handelt es sich z. B. bei COM\-Komponenten, ActiveX\-Schnittstellen und Win32\-API\-Funktionen.  
  
## In diesem Abschnitt  
 [Interoperating with Unmanaged Code How\-to Topics](http://msdn.microsoft.com/de-de/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Enthält Links zu allen Gewusst\-wie\-Themen in der Begriffsdokumentation zur Zusammenarbeit mit nicht verwaltetem Code.  
  
 [Verfügbarmachen von COM\-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Beschreibt, wie COM\-Komponenten in .NET Framework\-Anwendungen verwendet werden.  
  
 [Verfügbarmachen von .NET Framework\-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Beschreibt, wie .NET Framework\-Komponenten in COM\-Anwendungen verwendet werden.  
  
 [Verwenden nicht verwalteter DLL\-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Beschreibt das Aufrufen nicht verwalteter DLL\-Funktionen mithilfe von Plattformaufruf.  
  
 [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/de-de/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Bietet Tipps zum Schreiben integrierter COM\-Komponenten.  
  
 [Interop\-Marshalling](../../../docs/framework/interop/interop-marshaling.md)  
 Erläutert das Marshalling für COM\-Interop und Plattformaufruf.  
  
 [How to: Map HRESULTs and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Beschreibt die Übereinstimmung zwischen Ausnahmen und HRESULTs.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/de-de/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Beschreibt das Verhalten generischer Typen bei Verwendung mit COM\-Interop.  
  
## Verwandte Abschnitte  
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Stellt Links für weitere Informationen über das Einbinden von COM\-Komponenten in die .NET Framework\-Anwendung zur Verfügung.