---
title: Arbeiten mit Assemblys und dem globalen Assemblychache
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
ms.openlocfilehash: 7834fbc4d74b44c4bc5204ac451e92cac22e1ef5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645417"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a>Arbeiten mit Assemblys und dem globalen Assemblychache

Wenn Sie eine Assembly freigeben und für mehrere Anwendungen gemeinsam nutzen möchten, können Sie die Assembly im globalen Assemblycache installieren. Jeder Computer, auf dem die Common Language Runtime installiert ist, verfügt über diesen computerweiten Codecache. Im globalen Assemblycache werden Assemblys gespeichert, die speziell für die gemeinsame Verwendung durch mehrere Anwendungen auf dem Computer vorgesehen sind. Eine Assembly muss einen starken Namen haben, um im globalen Assemblycache installiert werden zu können.  
  
> [!NOTE]
> Bei Assemblys, die im globalen Assemblycache abgelegt werden, müssen Assembly- und Dateiname (ohne die Dateinamenerweiterung) übereinstimmen. Beispielsweise muss der Dateiname einer Assembly, die den Namen myAssembly hat, entweder myAssembly.exe oder myAssembly.dll lauten.  
  
Geben Sie Assemblys nur dann durch eine Installation im globalen Assemblycache frei, wenn dies unbedingt erforderlich ist. Wenn die Freigabe einer Assembly nicht unbedingt erforderlich ist, empfiehlt es sich, die Assemblyabhängigkeiten privat zu halten und Assemblys im Anwendungsverzeichnis abzulegen. Assemblys müssen außerdem nicht im globalen Assemblycache installiert sein, um für COM-Interop oder nicht verwalteten Code verfügbar zu sein.  
  
Es gibt verschiedene Gründe, eine Assembly im globalen Assemblycache zu installieren:  
  
- Freigegebener Standort.  
  
     Assemblys, die für die Verwendung durch Anwendungen vorgesehen sind, können im globalen Assemblycache installiert werden. Wenn beispielsweise alle Anwendungen eine im globalen Assemblycache befindliche Assembly verwenden sollen, kann der Datei Machine.config eine Versionsrichtlinienanweisung hinzugefügt werden, die Verweise auf die Assembly umleitet.  
  
- Dateisicherheit.  
  
     Administratoren verwenden zum Schutz des Verzeichnisses systemroot oft eine Zugriffssteuerungsliste (ACL, Access Control List), um Schreib- und Ausführungszugriffe zu steuern. Da der globale Assemblycache im Verzeichnis systemroot installiert ist, erbt er die ACL dieses Verzeichnisses. Aus diesem Grund empfiehlt es sich, nur Benutzern mit Administratorrechten das Löschen von Dateien aus dem globalen Assemblycache zu gestatten.  
  
- Paralleles Versioning.  
  
     Im globalen Assemblycache dürfen sich mehrere Assemblys mit demselben Namen befinden, solange sich ihre Versionsinformationen unterscheiden.  
  
- Zusätzliche Suchposition.  
  
     Die Common Language Runtime durchsucht den globalen Assemblycache nach der angeforderten Assembly, bevor CodeBase-Informationen in einer Konfigurationsdatei überprüft oder verwendet werden.  
  
 Beachten Sie, dass es Szenarien gibt, in denen eine Assembly ausdrücklich nicht im globalen Assemblycache installiert werden soll. Wenn Sie eine der Assemblys, aus denen eine Anwendung besteht, im globalen Assemblycache ablegen, können Sie die Anwendung anschließend weder replizieren noch installieren, indem Sie mit XCOPY das Anwendungsverzeichnis kopieren. In einem solchen Fall müssen Sie die Assembly ebenfalls im globalen Assemblycache ablegen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
[How to: Installieren einer Assembly im globalen Assemblycache](install-assembly-into-gac.md)  
Beschreibt die Möglichkeiten, eine Assembly im globalen Assemblycache zu installieren.  
  
[How to: Anzeigen der Inhalte des globalen Assemblycaches](how-to-view-the-contents-of-the-gac.md)  
Verwenden Sie das [Global Assembly Cache-Tool („gacutil.exe“)](../tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.  
  
[How to: Entfernen einer Assembly aus dem globalen Assemblycache](how-to-remove-an-assembly-from-the-gac.md)  
Verwenden Sie das [Global Assembly Cache-Tool („gacutil.exe“)](../tools/gacutil-exe-gac-tool.md), um eine Assembly aus dem globalen Assemblycache zu entfernen.  
  
[Verwenden von Serviced Components mit dem globalen Assemblycache](use-serviced-components-with-the-gac.md)  
Erläutert, warum Serviced Components (verwaltete COM+-Komponenten) im globalen Assemblycache abgelegt werden sollten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

[Erstellen von Assemblys](../../standard/assembly/create.md)  
Bietet eine Übersicht über das Erstellen von Assemblys.  
  
[Globaler Assemblycache](gac.md)  
Beschreibt den globalen Assemblycache.  
  
[How to: Anzeigen des Assemblyinhalts](../../standard/assembly/view-contents.md)  
Erläutert, wie der [IL-Disassembler („ildasm.exe“)](../tools/ildasm-exe-il-disassembler.md) verwendet wird, um Microsoft Intermediate Language-Informationen (MSIL) in einer Assembly anzuzeigen.  
  
[So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)  
Beschreibt, wie die Assemblys, die die Anwendung bilden, von der Common Language Runtime gesucht und geladen werden.  
  
[Programmieren mit Assemblys](../../standard/assembly/index.md)  
Beschreibt Assemblys, die die Bausteine verwalteter Anwendungen bilden.
