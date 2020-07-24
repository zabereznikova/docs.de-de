---
title: COM-Interop ohne Registrierung
description: In diesem Artikel erhalten Sie Informationen zur Verwendung von COM-Interop ohne Registrierung, um eine Komponente zu aktivieren, ohne die Windows-Registrierung zum Speichern von Assemblyinformationen zu verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], interop
- COM interop, registration-free COM interop
- registration-free COM interop
- manifests [.NET Framework]
- registration-free activation
- object activation
- registration-free COM interop, about registration-free COM interop
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
ms.openlocfilehash: c6a4dfc54152ade6136e4292bbd1c4522553d491
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281601"
---
# <a name="registration-free-com-interop"></a>COM-Interop ohne Registrierung
COM-Interop ohne Registrierung aktiviert eine Komponente, ohne die Windows-Registrierung zum Speichern von Assemblyinformationen zu verwenden. Statt eine Komponente auf einem Computer während der Bereitstellung zu registrieren, erstellen Sie zur Entwurfszeit Win32-Manifestdateien, die Informationen zur Bindung und Aktivierung enthalten. Diese Manifestdateien steuern anstelle der Registrierungsschlüssel die Aktivierung eines Objekts.  
  
 Die Aktivierung der Assemblys ohne Registrierung bietet im Vergleich zur Registrierung bei der Bereitstellung zwei Vorteile:  
  
- Sie können steuern, welche DLL-Version aktiviert wird, wenn mehrere Versionen auf einem Computer installiert sind.  
  
- Endbenutzer können mit XCOPY oder FTP die Anwendung in ein geeignetes Verzeichnis auf dem Computer kopieren. Die Anwendung kann dann von diesem Verzeichnis aus ausgeführt werden.  
  
 In diesem Abschnitt werden die beiden Arten von Manifesten beschrieben, die für COM-Interop ohne Registrierung erforderlich sind: Anwendungs- und Komponentenmanifeste. Diese Manifeste sind XML-Dateien. Ein Anwendungsmanifest, das von einem Anwendungsentwickler erstellt wird, enthält Metadaten zur Beschreibung von Assemblys und Assemblyabhängigkeiten. Ein Komponentenmanifest, das von einem Komponentenentwickler erstellt wird, enthält Informationen, die ansonsten in der Windows-Registrierung gespeichert sind.  
  
### <a name="requirements-for-registration-free-com-interop"></a>Anforderungen an COM-Interop ohne Registrierung  
  
1. Die Unterstützung für COM-Interop ohne Registrierung variiert je nach Typ der Bibliothekassembly und richtet sich insbesondere danach, ob die Assembly nicht verwaltet (parallele Ausführung für COM) oder verwaltet (.NET-basiert) ist. In der folgenden Tabelle werden die Anforderungen an das Betriebssystem und die .NET Framework-Version für jeden Assemblytyp aufgeführt.  
  
    |Assemblytyp|Betriebssystem|.NET Framework-Version|  
    |-------------------|----------------------|----------------------------|  
    |Parallele Ausführung für COM|Microsoft Windows XP|Nicht erforderlich|  
    |.NET-basiert|Windows XP mit SP2|.NET Framework 1.1 oder höher|  
  
     Die Windows Server 2003-Produktfamilie unterstützt auch COM-Interop ohne Registrierung für .NET-basierte Assemblys.  
  
     Damit eine .NET-basierte Klasse mit der Aktivierung ohne COM-Registrierung kompatibel ist, muss die Klasse über einen parameterlosen Konstruktor verfügen und öffentlich sein.  
  
### <a name="configuring-com-components-for-registration-free-activation"></a>Konfigurieren von COM-Komponenten für eine Aktivierung ohne Registrierung  
  
1. Damit eine COM-Komponente ohne Registrierung aktiviert werden kann, muss sie als parallele Assembly bereitgestellt werden. Parallele Assemblys sind nicht verwaltete Assemblys.  Weitere Informationen finden Sie unter [Verwenden paralleler Assemblys](/windows/desktop/SbsCs/using-side-by-side-assemblies).  
  
     Zur Verwendung paralleler COM-Assemblys muss ein Entwickler von .NET-basierten Anwendungen ein Anwendungsmanifest bereitstellen, das die Bindungs- und Aktivierungsinformationen enthält. Die Unterstützung nicht verwalteter paralleler Assemblys ist in Windows XP integriert. Die vom Betriebssystem unterstützte COM Runtime durchsucht ein Anwendungsmanifest nach Aktivierungsinformationen, wenn die aktivierte Komponente nicht in der Registrierung vorhanden ist.  
  
     Die Aktivierung ohne Registrierung ist für COM-Komponenten unter Windows XP optional. Detaillierte Anweisungen zum Hinzufügen einer parallelen Assembly zu einer Anwendung finden Sie unter [Verwenden paralleler Assemblys](/windows/desktop/SbsCs/using-side-by-side-assemblies).  
  
    > [!NOTE]
    > Die parallele Ausführung ist eine .NET Framework-Funktion, mit der mehrere Versionen der Common Language Runtime und mehrere Versionen von Anwendungen und Komponenten, die eine Version der Common Language Runtime verwenden, gleichzeitig auf demselben Computer ausgeführt werden können. Die parallele Ausführung und parallele Assemblys sind unterschiedliche Mechanismen für die Bereitstellung paralleler Funktionen.  
  
## <a name="see-also"></a>Siehe auch

- [How to: Konfigurieren von .NET Framework-basierten COM-Komponenten für die Aktivierung ohne Registrierung](configure-net-framework-based-com-components-for-reg.md)
