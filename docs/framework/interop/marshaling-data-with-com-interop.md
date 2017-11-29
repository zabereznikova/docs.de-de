---
title: Marshallen von Daten mit COM-Interop
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2def27790a1727bda524b8c14a93f7b78127a569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-com-interop"></a>Marshallen von Daten mit COM-Interop
COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM. Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] umfasst die folgenden COM-Interop-Tools:  
  
-   [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert. Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.  
  
-   [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.  
  
 In den folgenden Abschnitten link zu Themen über die Prozesse zum Anpassen von Interop-Wrappern, wenn Sie den Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
[Vorgehensweise: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md)   
Beschreibt, wie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen. 
 
 [How to: Migrate Managed-Code DCOM to WCF (Vorgehensweise: Migrieren von verwaltetem Code DCOM zu WCF)](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [COM-Datentypen](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)  
 Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.  
  
 [Anpassen von COM-Aufrufwrappern](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)  
 Beschreibt, wie Sie explizites Marshalling von Datentypen mithilfe der <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut zur Entwurfszeit.  
  
 [Anpassen von Runtime Callable Wrappers](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)  
 Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.  
  
 [Erweiterte COM-Interoperabilität](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)  
 Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.  
  
 [Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)  
 Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.  
  
 [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)  
 Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.  
  
 [Interoperation mit generischen Typen](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)  
 Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.
