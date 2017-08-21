---
title: Assemblys in der Common Language Runtime (CLR)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.assetid: 2cfebe19-7436-49f1-bd99-3c4019f0b676
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: faa41efa7f3ad898557e966d141aa8f5108d60bd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="assemblies-in-the-common-language-runtime"></a>Assemblys in der Common Language Runtime (CLR)
Assemblys sind die Bausteine von .NET Framework-Anwendungen; sie bilden das Fundament für Bereitstellung, Versionskontrolle, Wiederverwendung, Gültigkeitsbereiche für die Aktivierung und Sicherheitsberechtigungen. Eine Assembly ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden. Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.  
  
 Eine Assembly führt die folgenden Funktionen aus:  
  
-   Sie enthält Code, der von der Common Language Runtime ausgeführt wird. MSIL-Code (Microsoft Intermediate Language) in einer übertragbaren ausführbaren Datei (Portable Executable, PE) wird nicht ausgeführt, wenn diesem kein Assemblymanifest zugeordnet wurde. Beachten Sie, dass jede Assembly nur über einen Einstiegspunkt (`DllMain`, `WinMain` oder `Main`) verfügen kann.  
  
-   Sie bildet eine Sicherheitsgrenze. Eine Assembly ist die Einheit, bei der Berechtigungen angefordert und erteilt werden. Weitere Informationen über Sicherheitsgrenzen bei Assemblys finden Sie unter [Überlegungen zur Assemblysicherheit](../../../docs/framework/app-domains/assembly-security-considerations.md).  
  
-   Sie bildet eine Typgrenze. Die Identität jedes Typs enthält den Namen der Assembly, in der dieser sich befindet. Wenn der Typ `MyType` in den Gültigkeitsbereich einer Assembly geladen wird, ist dieser nicht derselbe wie der Typ `MyType`, der in den Gültigkeitsbereich einer anderen Assembly geladen wurde.  
  
-   Sie bildet eine Grenze für den Gültigkeitsbereich von Verweisen. Das Assemblymanifest enthält Assemblymetadaten, die für das Auflösen von Typen und die Bereitstellung angeforderter Ressourcen verwendet werden. Sie gibt die Typen und Ressourcen an, die außerhalb der Assembly verfügbar gemacht werden. Das Manifest listet außerdem andere Assemblys auf, von denen sie abhängig ist.  
  
-   Sie bildet eine Versionsgrenze. Die Assembly ist die kleinste, in verschiedenen Versionen verwendbare Einheit in der Common Language Runtime. Alle Typen und Ressourcen in derselben Assembly bilden eine Einheit mit derselben Version. Das Assemblymanifest beschreibt die von Ihnen für abhängige Assemblys angegebenen Versionsabhängigkeiten. Weitere Informationen über die Versionen finden Sie unter [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md).  
  
-   Sie bildet eine Bereitstellungseinheit. Beim Starten einer Anwendung müssen nur die von der Anwendung zu Beginn aufgerufenen Assemblys vorhanden sein. Andere Assemblys, z. B. Lokalisierungsressourcen oder Assemblys mit Hilfsklassen, können bei Bedarf abgerufen werden. Dadurch ist die Anwendung beim ersten Herunterladen einfach und schlank. Weitere Informationen über die Bereitstellung von Assemblys finden Sie unter [Bereitstellung von Anwendungen](../../../docs/framework/deployment/index.md).  
  
-   Sie stellt die Einheit dar, in der die parallele Ausführung unterstützt wird. Weitere Informationen über das Ausführen mehrerer Versionen einer Assembly finden Sie unter [Assemblys und parallele Ausführung](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md).  
  
 Assemblys können statisch oder dynamisch sein. Statische Assemblys können .NET Framework-Typen (Schnittstellen und Klassen) sowie Ressourcen für die Assembly (Bitmaps, JPEG-Dateien, Ressourcendateien usw.) enthalten. Statische Assemblys werden auf dem Datenträger in PE-Dateien (Portable Executable, übertragbare ausführbare Datei) gespeichert. Mit .NET Framework können Sie außerdem dynamische Assemblys erstellen, die direkt vom Arbeitsspeicher aus ausgeführt und vor der Ausführung nicht auf dem Datenträger gespeichert werden. Dynamische Assemblys können nach ihrer Ausführung auf dem Datenträger gespeichert werden.  
  
 Beim Erstellen von Assemblys stehen Ihnen verschiedene Möglichkeiten zur Verfügung: Um DLL-Dateien oder EXE-Dateien zu erstellen, verwenden Sie wie gewohnt Entwicklungstools wie z. B. Visual Studio. Mit den Tools von [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] können Sie Assemblys mit Modulen erstellen, die in anderen Entwicklungsumgebungen erzeugt wurden. Außerdem können Sie dynamische Assemblys auch mit Common Language Runtime-APIs wie <xref:System.Reflection.Emit?displayProperty=fullName> erstellen.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Assemblyinhalte](../../../docs/framework/app-domains/assembly-contents.md)|Beschreibt die Elemente, aus denen die Assembly besteht.|  
|[Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md)|Beschreibt die Daten im Assemblymanifest und wie diese in Assemblys gespeichert werden.|  
|[Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)|Beschreibt den globalen Assemblycache und dessen Verwendung mit Assemblys.|  
|[Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md)|Beschreibt die Eigenschaften von Assemblys mit starken Namen.|  
|[Überlegungen zur Assemblysicherheit](../../../docs/framework/app-domains/assembly-security-considerations.md)|Erörtert die Sicherheitsmechanismen von Assemblys.|  
|[Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md)|Bietet eine Übersicht über die Versionskontrollrichtlinien von .NET Framework.|  
|[Assemblypositionierung](../../../docs/framework/app-domains/assembly-placement.md)|Erörtert die Positionierung von Assemblys.|  
|[Assemblys und parallele Ausführung](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)|Bietet eine Übersicht über das gleichzeitige Verwenden mehrerer Versionen der Laufzeit oder einer Assembly.|  
|[Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)|Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.|  
|[Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Beschreibt das Erstellen dynamischer Assemblys.|  
|[So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|Beschreibt, wie .NET Framework zur Laufzeit Assemblyverweise auflöst.|  
  
## <a name="reference"></a>Verweis  
 <xref:System.Reflection.Assembly?displayProperty=fullName>

