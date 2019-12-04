---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 186ce5ae3087fd9b4c7e5c32e110de4bc7d5e578
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801984"
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie ein Windows Communication Foundation (WCF)-Dienst Bibliotheksprojekt bereitstellen können.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  
 Eine WCF-Dienst Bibliothek ist eine Dynamic Link Library (dll). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Prozess finden Sie unter [Hosting und Nutzung von WCF-Diensten](https://docs.microsoft.com/previous-versions/dotnet/articles/bb332338(v=msdn.10)).  
  
 Eine WCF-Dienst Bibliothek kann wie jeder andere WCF-Dienst bereitgestellt werden. Beachten Sie jedoch, dass .NET Framework die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Das WCF-Dienst Bibliotheksprojekt verringert diese Einschränkung durch Bereitstellen einer App. config-Datei für die Bibliothek während der Entwicklung. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
