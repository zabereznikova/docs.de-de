---
title: Globaler Assemblycache | Microsoft-Dokumentation
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
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0a40c6dcc51728bb069381b8af4652ce533bb08c
ms.contentlocale: de-de
ms.lasthandoff: 06/02/2017

---
# <a name="global-assembly-cache"></a>Globaler Assemblycache
Jeder Computer, auf dem die Common Language Runtime installiert ist, besitzt einen computerweiten Codecache, den so genannten globalen Assemblycache. Im globalen Assemblycache werden Assemblys gespeichert, die speziell für die gemeinsame Verwendung durch mehrere Anwendungen auf dem Computer vorgesehen sind.  
  
 Geben Sie Assemblys nur dann durch eine Installation im globalen Assemblycache frei, wenn dies unbedingt erforderlich ist. Wenn die Freigabe einer Assembly nicht unbedingt erforderlich ist, empfiehlt es sich, die Assemblyabhängigkeiten privat zu halten und Assemblys im Anwendungsverzeichnis abzulegen. Assemblys müssen außerdem nicht im globalen Assemblycache installiert sein, um für COM-Interop oder nicht verwalteten Code verfügbar zu sein.  
  
> [!NOTE]
>  Es gibt Szenarien, in denen eine Assembly ausdrücklich nicht im globalen Assemblycache installiert werden soll. Wenn Sie eine der Assemblys, aus denen eine Anwendung besteht, im globalen Assemblycache ablegen, können Sie die Anwendung anschließend weder replizieren noch installieren, indem Sie mit dem **xcopy**-Befehl das Anwendungsverzeichnis kopieren. Sie müssen die Assembly zusätzlich in den globalen Assemblycache verschieben.  
  
 Es gibt zwei Möglichkeiten für die Bereitstellung einer Assembly im globalen Assemblycache:  
  
-   Die Verwendung eines Installationsprogramms, das für die Zusammenarbeit mit dem globalen Assemblycache entworfen wurde. Das ist die bevorzugte Option für die Installation von Assemblys im globalen Assemblycache.  
  
-   Die Verwendung des Entwicklertools [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) aus [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].  
  
    > [!NOTE]
    >  Bei Bereitstellungsszenarien sollten Sie Assemblys mit Windows Installer im globalen Assemblycache installieren. Da das Global Assembly Cache-Tool nur die Assemblyverweiszählung und andere von Windows Installer bereitgestellte Funktionen unterstützt, sollten Sie das Tool nur in Entwicklungsszenarien verwenden.  
  
 Ab .NET Framework 4 lautet die Standardposition des globalen Assemblycache **%windir%\Microsoft.NET\assembly**. In früheren Versionen von .NET Framework lautet der Standardspeicherort **%windir%\assembly**.  
  
 Administratoren verwenden zum Schutz des Verzeichnisses systemroot oftmals eine Zugriffssteuerungsliste (ACL – Access Control List), um Schreib- und Ausführungszugriffe zu kontrollieren. Da der globale Assemblycache in einem Unterverzeichnis des Verzeichnisses systemroot installiert ist, erbt er die ACL dieses Verzeichnisses. Aus diesem Grund empfiehlt es sich, nur Benutzern mit Administratorrechten das Löschen von Dateien aus dem globalen Assemblycache zu gestatten.  
  
 Alle Assemblys, die im globalen Assemblycache bereitgestellt werden, müssen starke Namen besitzen. Beim Hinzufügen einer Assembly zum globalen Assemblycache werden Integritätsprüfungen für alle Dateien vorgenommen, aus denen die Assembly besteht. Diese Integritätsprüfungen werden vom Cache durchgeführt, um sicherzustellen, dass eine Assembly nicht manipuliert wurde (z. B. wenn eine Datei geändert wurde, aber das Manifest diese Änderung nicht widerspiegelt).  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md)
