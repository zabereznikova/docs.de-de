---
title: Marshallen von Daten mit COM-Interop
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 807e514fac7d33cdacac3a48a37c7aa8dd92ef9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648646"
---
# <a name="marshaling-data-with-com-interop"></a>Marshallen von Daten mit COM-Interop
COM-Interop bietet Unterstützung für sowohl die Verwendung von COM-Objekten aus verwaltetem Code als auch das Bereitstellen verwalteter Objekte für COM. Die Unterstützung für das Marshalling von Daten zu und von COM ist umfangreich und stellt fast immer das richtige Marshallingverhalten bereit.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] umfasst die folgenden COM-Interop-Tools:  
  
- [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), der eine COM-Typbibliothek in eine Interop-Assembly konvertiert. Aus dieser Assembly generiert der Interop-Marshallingdienst Wrapper, die Datenmarshalling zwischen verwaltetem und nicht verwaltetem Speicher ausführen.  
  
- [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), der eine COM-Typbibliothek aus einer Assembly erzeugt und einen Wrapper generiert, der Marshalling während Methodenaufrufen ausführt.  
  
 Die folgenden Abschnitte verweisen auf Themen, in denen die Prozesse zum Anpassen von Interop-Wrappern beschrieben werden, wenn Sie dem Marshaller zusätzliche Typinformationen bereitstellen können (oder müssen).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
[Vorgehensweise: Manuelles Erstellen von Wrappern](how-to-create-wrappers-manually.md)   
Beschreibt, wie Sie einen COM-Wrapper in verwaltetem Quellcode manuell erstellen. 
 
 [Vorgehensweise: Migrieren von verwaltetem Code DCOM zu WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Beschreibt, wie Sie verwalteten DCOM-Code zu WCF für die sicherste Lösung migrieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [COM-Datentypen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))  
 Stellt die entsprechenden verwalteten und nicht verwalteten Datentypen bereit.  
  
 [Anpassen von COM-Aufrufwrappern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))  
 Beschreibt, wie Sie Datentypen mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs zur Entwurfszeit explizit marshallen.  
  
 [Anpassen von Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))  
 Beschreibt, wie das Marshallingverhalten von Typen in einer Interop-Assembly angepasst und COM-Typen manuell definiert werden.  
  
 [Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))  
 Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.  
  
 [Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))  
 Beschreibt den Konvertierungsprozess beim Export einer Assembly in eine Typbibliothek.  
  
 [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))  
 Beschreibt den Konvertierungsprozess beim Import einer Typbibliothek in eine Assembly.  
  
 [Interoperation mit generischen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))  
 Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.
