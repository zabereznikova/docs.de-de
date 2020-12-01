---
title: Globaler Assemblycache
description: Grundlegendes zum globalen Assemblycache, ein computerweiter Codecache, in dem die Common Language Runtime für .NET installiert ist
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
ms.openlocfilehash: 57d18c01bd6261e8207d8ad3849a3a7da9a24b6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264607"
---
# <a name="global-assembly-cache"></a>Globaler Assemblycache

Jeder Computer, auf dem die Common Language Runtime installiert ist, besitzt einen computerweiten Codecache, den so genannten globalen Assemblycache. Im globalen Assemblycache werden Assemblys gespeichert, die speziell für die gemeinsame Verwendung durch mehrere Anwendungen auf dem Computer vorgesehen sind.  
  
 Geben Sie Assemblys nur dann durch eine Installation im globalen Assemblycache frei, wenn dies unbedingt erforderlich ist. Wenn die Freigabe einer Assembly nicht unbedingt erforderlich ist, empfiehlt es sich, die Assemblyabhängigkeiten privat zu halten und Assemblys im Anwendungsverzeichnis abzulegen. Assemblys müssen außerdem nicht im globalen Assemblycache installiert sein, um für COM-Interop oder nicht verwalteten Code verfügbar zu sein.  
  
> [!NOTE]
> Es gibt Szenarios, in denen eine Assembly ausdrücklich nicht im globalen Assemblycache installiert werden soll. Wenn Sie eine der Assemblys, aus denen eine Anwendung besteht, im globalen Assemblycache ablegen, können Sie die Anwendung anschließend weder replizieren noch installieren, indem Sie mit dem **xcopy**-Befehl das Anwendungsverzeichnis kopieren. Sie müssen die Assembly zusätzlich in den globalen Assemblycache verschieben.  
  
 Es gibt zwei Möglichkeiten für die Bereitstellung einer Assembly im globalen Assemblycache:  
  
- Die Verwendung eines Installationsprogramms, das für die Zusammenarbeit mit dem globalen Assemblycache entworfen wurde. Das ist die bevorzugte Option für die Installation von Assemblys im globalen Assemblycache.  
  
- Die Verwendung des Entwicklertools [Global Assembly Cache-Tool („Gacutil.exe“)](../tools/gacutil-exe-gac-tool.md) aus dem Windows SDK.  
  
    > [!NOTE]
    > Bei Bereitstellungsszenarios sollten Sie Assemblys mit Windows Installer im globalen Assemblycache installieren. Verwenden Sie das Global Assembly Cache-Tool nur in Entwicklungsszenarios, da es weder die Assemblyverweiszählung noch weitere bei Verwendung des Windows Installer bereitgestellte Features unterstützt.  
  
 Ab .NET Framework 4 lautet der Standardspeicherort des globalen Assemblycaches **%windir%\Microsoft.NET\assembly**. In früheren Versionen von .NET Framework lautet der Standardspeicherort **%windir%\assembly**.  
  
 Administratoren verwenden zum Schutz des Verzeichnisses systemroot oftmals eine Zugriffssteuerungsliste (ACL – Access Control List), um Schreib- und Ausführungszugriffe zu kontrollieren. Da der globale Assemblycache in einem Unterverzeichnis des Verzeichnisses „Systemstamm“ installiert ist, erbt er die ACL dieses Verzeichnisses. Aus diesem Grund wird empfohlen, nur Benutzern mit Administratorrechten das Löschen von Dateien aus dem globalen Assemblycache zu gestatten.  
  
 Alle Assemblys, die im globalen Assemblycache bereitgestellt werden, müssen starke Namen besitzen. Beim Hinzufügen einer Assembly zum globalen Assemblycache werden Integritätsprüfungen für alle Dateien vorgenommen, aus denen die Assembly besteht. Diese Integritätsprüfungen werden vom Cache durchgeführt, um sicherzustellen, dass eine Assembly nicht manipuliert wurde (z. B. wenn eine Datei geändert wurde, aber das Manifest diese Änderung nicht widerspiegelt).  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../standard/assembly/index.md)
- [Arbeiten mit Assemblys und dem globalen Assemblychache](working-with-assemblies-and-the-gac.md)
- [Assemblys mit starkem Namen](../../standard/assembly/strong-named.md)
