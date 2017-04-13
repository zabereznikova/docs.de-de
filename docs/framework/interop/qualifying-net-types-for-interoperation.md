---
title: "Qualifying .NET Types for Interoperation | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "COM interop, qualifying .NET types"
  - "qualifying .NET types for interoperation"
  - "interoperation with unmanaged code, qualifying .NET types"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Qualifying .NET Types for Interoperation
Wenn Sie Typen in einer Assembly für COM\-Anwendungen verfügbar machen möchten, müssen die Voraussetzungen von COM\-Interop zur Entwurfszeit erfüllt sein.  Verwaltete Typen \(Klasse, Schnittstelle, Struktur und Enumeration\) können nahtlos in COM\-Typen integriert werden, wenn Sie folgende Richtlinien beachten:  
  
-   Klassen müssen Schnittstellen explizit implementieren.  
  
     Obwohl in COM\-Interop die Möglichkeit besteht, automatisch eine Schnittstelle zu generieren, die alle Member der Klasse und die der Basisklasse enthält, empfiehlt sich die Verwendung expliziter Schnittstellen.  Die automatisch generierte Schnittstelle wird als Klassenschnittstelle bezeichnet.  Die Richtlinien finden Sie unter [Einführung in die Klassenschnittstelle](http://msdn.microsoft.com/de-de/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
     Zum Einbinden von Schnittstellendefinitionen in den Code können Sie [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# und C\+\+ verwenden und müssen nicht IDL \(Interface Definition Language\) oder eine Entsprechung verwenden.  Detaillierte Informationen zur Syntax finden Sie in der Dokumentation zur Sprache.  
  
-   Verwaltete Typen müssen öffentlich sein.  
  
     Nur öffentliche Typen in einer Assembly werden registriert und in die Typbibliothek exportiert.  Daher werden auch nur öffentliche Typen in COM angezeigt.  
  
     Verwaltete Typen machen Funktionen für anderen verwalteten Code verfügbar, der möglicherweise nicht für COM verfügbar ist.  Beispielsweise werden parametisierte Konstruktoren, statische Methoden und konstante Felder nicht für COM\-Clients verfügbar gemacht.  Da Daten von Common Language Runtime innerhalb und außerhalb eines Typs gemarshallt werden, können diese auch kopiert oder umgewandelt werden.  
  
-   Alle Methoden, Eigenschaften, Felder und Ereignisse müssen öffentlich sein.  
  
     Die Member öffentlicher Typen müssen ebenfalls öffentlich sein, damit sie in COM angezeigt werden können.  Sie können die Sichtbarkeit einer Assembly, eines öffentlichen Typs oder dessen öffentlicher Member mit <xref:System.Runtime.InteropServices.ComVisibleAttribute> einschränken.  Standardmäßig werden alle öffentlichen Typen und Member angezeigt.  
  
-   Der Standardkonstruktor der Typen muss öffentlich sein und in COM aktiviert werden.  
  
     Verwaltete, öffentliche Typen sind in COM sichtbar.  Allerdings können COM\-Clients den Typ ohne öffentlichen Standardkonstruktor \(ein Konstruktor ohne Argumente\) nicht erstellen.  COM\-Clients können den Typ aber trotzdem verwenden, wenn er auf andere Weise aktiviert wird.  
  
-   Typen können nicht abstrakt sein.  
  
     Weder COM\-Clients noch .NET\-Clients können abstrakte Typen erstellen.  
  
 Die Vererbungshierarchie eines verwalteten Typs wird beim Exportieren in COM vereinfacht.  Zwischen verwalteten und nicht verwalteten Umgebungen bestehen außerdem Unterschiede im Versioning.  In COM verfügbar gemachte Typen haben andere Charakteristiken beim Versioning als andere verwaltete Typen.  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/de-de/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Applying Interop Attributes](../../../docs/framework/interop/applying-interop-attributes.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)