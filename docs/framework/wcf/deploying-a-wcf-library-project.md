---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 0400fc9ec5a5629139348709bbd3a5554ce251c7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593352"
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie ein Windows Communication Foundation (WCF)-Dienst-Bibliotheksprojekt bereitstellen können.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  
 Eine WCF-Dienstbibliothek ist eine Dynamic Link Library (DLL). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Prozess finden Sie unter [hosten und Nutzen von WCF-Dienste](https://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Eine WCF-Dienstbibliothek kann wie jeder andere WCF-Dienst bereitgestellt werden. Bedenken Sie jedoch, dass .NET Framework die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Der WCF-Dienstbibliotheksprojekt behebt diese Einschränkung durch die Bereitstellung einer App.config-Datei für die Bibliothek während der Entwicklung. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
