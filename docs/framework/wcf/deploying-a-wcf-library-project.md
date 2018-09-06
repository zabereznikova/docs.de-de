---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 1ba26a7e68fe262dc5f4f569647af1ebb94e03a8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042529"
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie ein Windows Communication Foundation (WCF)-Dienst-Bibliotheksprojekt bereitstellen können.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  
 Eine WCF-Dienstbibliothek ist eine Dynamic Link Library (DLL). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Prozess finden Sie unter [hosten und Nutzen von WCF-Dienste](https://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Eine WCF-Dienstbibliothek kann wie jeder andere WCF-Dienst bereitgestellt werden. Beachten Sie jedoch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Der WCF-Dienstbibliotheksprojekt behebt diese Einschränkung durch die Bereitstellung einer App.config-Datei für die Bibliothek während der Entwicklung. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
