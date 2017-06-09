---
title: "Marshaling Data with COM Interop | Microsoft Docs"
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
  - "COM interop, data marshaling"
  - "marshaling data, COM interop"
ms.assetid: 0bcdd7bf-5026-43eb-b08b-f03f90db9df9
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Marshaling Data with COM Interop
COM\-Interop bietet Unterstützung für sowohl die Verwendung von COM\-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM.  Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] umfasst die folgenden COM\-Interop\-Tools:  
  
-   [Type Library Importer \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), der eine COM\-Typbibliothek in eine Interop\-Assembly konvertiert.  Aus dieser Assembly generiert der Interop\-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.  
  
-   [Type Library Exporter\-Tool \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), der eine COM\-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.  
  
 Dieser Abschnitt beschreibt die Prozesse zum Anpassen von Interop\-Wrappern, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können \(oder müssen\).  
  
## In diesem Abschnitt  
 [COM\-Datentypen](http://msdn.microsoft.com/de-de/f93ae35d-a416-4218-8700-c8218cc90061)  
 Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.  
  
 [Anpassen von COM\-Aufrufwrappern](http://msdn.microsoft.com/de-de/825177d3-4b2c-4723-82be-ce6ca2c34ace)  
 Beschreibt, wie Sie Datentypen mithilfe des **MarshalAsAttribute**\-Attributs zur Entwurfszeit explizit marshallen.  
  
 [Anpassen von Runtime Callable Wrappers](http://msdn.microsoft.com/de-de/4652beaf-77d0-4f37-9687-ca193288c0be)  
 Beschreibt, wie das Marshallingverhalten von Typen in einer Interop\-Assembly angepasst und COM\-Typen manuell definiert werden.  
  
 [Gewusst wie: Migrieren von verwaltetem Code DCOM zu WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Beschreibt, wie Sie verwalteten DCOM\-Code zu WCF für die sicherste Lösung migrieren.  
  
## Verwandte Abschnitte  
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Stellt Links zu weiteren Informationen über das Einbinden von COM\-Komponenten in Ihre .NET Framework\-Anwendung bereit.  
  
 [Assembly to Type Library Conversion Summary](http://msdn.microsoft.com/de-de/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.  
  
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/de-de/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/de-de/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM\-Interoperabilität unterstützt werden.