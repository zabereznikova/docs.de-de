---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbddd99125e8615640ca39d091e92cdde87c9faf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstbibliotheksprojekt bereitstellen.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  
 Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek ist eine Dynamic Link Library (DLL). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Vorgang finden Sie unter [Hosting und Verwenden von WCF-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliothek kann wie jeder andere [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst bereitgestellt werden. Beachten Sie jedoch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstbibliotheksprojekt umgeht diese Beschränkung, indem es während der Entwicklung die Datei app.config für die Bibliothek bereitstellt. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
