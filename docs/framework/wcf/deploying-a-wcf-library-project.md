---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: fb400a4d1ebba691222ad7fc9d2c09f1051591da
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803022"
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie einen Windows Communication Foundation (WCF)--Dienstbibliotheksprojekt bereitstellen können.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  
 Eine WCF-Dienstbibliothek ist eine Dynamic Link Library (DLL). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Vorgang finden Sie unter [Hosting und Verwenden von WCF-Webdiensten](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Eine WCF-Dienstbibliothek kann wie jeder andere WCF-Dienst bereitgestellt werden. Beachten Sie jedoch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Das WCF-Dienst-Bibliotheksprojekt entfällt diese Einschränkung durch eine Datei "App.config" für die Bibliothek während der Entwicklung bereitstellen. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
