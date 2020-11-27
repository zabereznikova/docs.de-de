---
title: Bereitstellen eines WCF-Bibliotheksprojekts
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: e3a90f03639a888b4528a1962a24b7adc5d43c58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260889"
---
# <a name="deploying-a-wcf-library-project"></a>Bereitstellen eines WCF-Bibliotheksprojekts

In diesem Thema wird beschrieben, wie Sie ein Windows Communication Foundation (WCF)-Dienst Bibliotheksprojekt bereitstellen können.  
  
## <a name="deploying-a-wcf-service-library"></a>Bereitstellen einer WCF-Dienstbibliothek  

 Eine WCF-Dienst Bibliothek ist eine Dynamic Link Library (dll). Als solche kann sie nicht eigenständig ausgeführt werden. Sie muss vielmehr in einer Hostumgebung bereitgestellt werden. Weitere Informationen zu diesem Prozess finden Sie unter [Hosting und Nutzung von WCF-Diensten](/previous-versions/dotnet/articles/bb332338(v=msdn.10)).  
  
 Eine WCF-Dienst Bibliothek kann wie jeder andere WCF-Dienst bereitgestellt werden. Beachten Sie jedoch, dass .NET Framework die Konfiguration für DLLs nicht unterstützt. <xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne. Das WCF-Dienst Bibliotheksprojekt verringert diese Einschränkung durch Bereitstellen einer App.config-Datei für die Bibliothek während der Entwicklung. Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen. Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren. Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.
