---
title: Einführung in COM-Interop
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 6c7caf266514c43e40135b33d848a688546acf1c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396778"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Einführung in COM-Interop (Visual Basic)
Der Component Object Model (com) ermöglicht einem Objekt, seine Funktionalität für andere Komponenten und für das Hosten von Anwendungen verfügbar zu machen. Obwohl COM-Objekte seit vielen Jahren für die Windows-Programmierung von grundlegender Bedeutung waren, bieten Anwendungen, die für die Common Language Runtime (CLR) entwickelt wurden, viele Vorteile.  
  
 .NET Framework Anwendungen ersetzen schließlich die mit com entwickelten. Bis dahin müssen Sie möglicherweise com-Objekte mithilfe von Visual Studio verwenden oder erstellen. Interoperabilität mit com oder *COM-Interop*ermöglicht es Ihnen, vorhandene COM-Objekte zu verwenden, während Sie in Ihrem eigenen Tempo auf die .NET Framework übergehen.  
  
 Wenn Sie die .NET Framework zum Erstellen von COM-Komponenten verwenden, können Sie COM-Interop ohne Registrierung verwenden. Auf diese Weise können Sie steuern, welche DLL-Version aktiviert ist, wenn mehr als eine Version auf einem Computer installiert ist, und Endbenutzer können mit XCopy oder FTP Ihre Anwendung in ein entsprechendes Verzeichnis auf dem Computer kopieren, auf dem Sie ausgeführt werden kann. Weitere Informationen finden Sie unter [COM-Interop ohne Registrierung](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Verwalteter Code und Daten  
 Der Code, der für die .NET Framework entwickelt wurde, wird als *verwalteter Code*bezeichnet und enthält Metadaten, die von der CLR verwendet werden. Daten, die von .NET Framework Anwendungen verwendet werden, werden als *verwaltete Daten* bezeichnet, da die Laufzeit datenbezogene Aufgaben verwaltet, z. b. das zuordnen und Freigeben von Arbeitsspeicher und das Ausführen der Typüberprüfung Standardmäßig verwendet Visual Basic .NET verwalteten Code und Daten, aber Sie können auf den nicht verwalteten Code und die Daten von COM-Objekten mithilfe von Interop-Assemblys zugreifen (die weiter unten auf dieser Seite beschrieben werden).  
  
## <a name="assemblies"></a>Assemblys  
 Eine Assembly ist der primäre Baustein einer .NET Framework-Anwendung. Dabei handelt es sich um eine Sammlung von Funktionen, die erstellt, mit Versions Angabe versehen und als eine einzelne Implementierungs Einheit bereitgestellt wird, die eine oder mehrere Dateien enthält. Jede Assembly enthält ein Assemblymanifest.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Typbibliotheken und Assemblymanifeste  
 Typbibliotheken beschreiben Merkmale von COM-Objekten, z. b. Elementnamen und Datentypen. Assemblymanifeste führen dieselbe Funktion für .NET Framework-Anwendungen aus. Sie enthalten Informationen zu folgenden Informationen:  
  
- Assemblyidentität, Version, Kultur und digitale Signatur.  
  
- Dateien, aus denen die Assemblyimplementierung besteht.  
  
- Typen und Ressourcen, aus denen die Assembly besteht. Dies schließt diejenigen ein, die daraus exportiert werden.  
  
- Abhängigkeiten der Kompilierzeit von anderen Assemblys.  
  
- Erforderliche Berechtigungen, damit die Assembly ordnungsgemäß ausgeführt wird.  
  
 Weitere Informationen zu Assemblys und Assemblymanifesten finden Sie unter Assemblys [in .net](../../../standard/assembly/index.md)  
  
### <a name="importing-and-exporting-type-libraries"></a>Importieren und Exportieren von Typbibliotheken  
 Visual Studio enthält ein Hilfsprogramm (Tlbimp), mit dem Sie Informationen aus einer Typbibliothek in eine .NET Framework Anwendung importieren können. Mithilfe des Hilfsprogramms Tlbexp können Sie Typbibliotheken aus Assemblys generieren.  
  
 Weitere Informationen zu Tlbimp und Tlbexp finden Sie unter [Tlbimp. exe (Typbibliothek-Import Programm)](../../../framework/tools/tlbimp-exe-type-library-importer.md) und [Tlbexp. exe (Type Library Exporter)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Interopassemblys  
 Interop-Assemblys sind .NET Framework Assemblys, die zwischen verwaltetem und nicht verwaltetem Code überbrücken und com-Objektmember entsprechenden .NET Framework verwalteten Membern Durch Visual Basic .NET erstellte Interop-Assemblys verarbeiten viele Details der Verwendung von COM-Objekten, z. b. Interoperabilitäts Marshalling.  
  
## <a name="interoperability-marshaling"></a>Interoperabilitätsmarshalling  
 Alle .NET Framework Anwendungen haben gemeinsam eine Reihe allgemeiner Typen gemeinsam, die eine Interoperabilität von Objekten ermöglichen, unabhängig von der verwendeten Programmiersprache. Bei den Parametern und Rückgabe Werten von COM-Objekten werden manchmal Datentypen verwendet, die sich von den in verwaltetem Code verwendeten unterscheiden. Beim *Interoperabilitätsmarshalling* werden Parameter und Rückgabewerte in äquivalente Datentypen verpackt, wenn Sie zu und von COM-Objekten wechseln. Weitere Informationen finden Sie unter [Interop](../../../framework/interop/interop-marshaling.md)-Marshalling.  
  
## <a name="see-also"></a>Weitere Informationen

- [COM-Interop](index.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](walkthrough-implementing-inheritance-with-com-objects.md)
- [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md)
- [Problembehandlung bei der Interoperabilität](troubleshooting-interoperability.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Interop Marshaling (Interop-Marshalling)](../../../framework/interop/interop-marshaling.md)
- [COM-Interop ohne Registrierung](../../../framework/interop/registration-free-com-interop.md)
