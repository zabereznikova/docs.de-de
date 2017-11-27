---
title: "Kernkommunikationen: Webhost-Unterstützung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6697df69f7397514972e64d6845298c090af379f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="core-communications-webhost-support"></a>Kernkommunikationen: Webhost-Unterstützung
In diesem Thema werden alle Ausnahmen aufgelistet, die von der Webhost-Unterstützung generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Dieser Dienst erfordert ASP.NET-Kompatibilität. Er muss außerdem in IIS gehostet werden. Hosten Sie den Dienst entweder in ISS mit aktivierter ASP.NET-Kompatibilität in der Web.config-Datei, oder legen Sie die AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode-Eigenschaft auf einen anderen Wert als "Erforderlich" fest.|  
|Hosting_ListenerNotFoundForActivationInRecycling|Kein Kanal führt an der angegebenen Adresse aktiv eine Überwachung aus. Wenn eine Anwendung wiederverwendet wird, wird der Dienst geschlossen.|  
|Hosting_NonHTTPInCompatibilityMode|Die einzigen Protokolle, die unter ASP.NET-Kompatibilität unterstützt werden, sind HTTP und HTTPS. Entfernen Sie den angegebenen Endpunkt, oder deaktivieren Sie ASP.NET-Kompatibilität für die Anwendung.|  
|Hosting_ProcessNotExecutingUnderHostedContext|Der angegebene Hosting-Prozess kann innerhalb der aktuellen Hostumgebung nicht aufgerufen werden. Diese API erfordert, dass die aufrufende Anwendung in Internet Information Services (IIS) oder Windows Process Activation Service (WAS) gehostet wird.|  
|Hosting_ServiceCompatibilityRequire|Der Dienst kann nicht aktiviert werden, da er ASP.NET-Kompatibilität erfordert. ASP.NET-Kompatibilität ist für diese Anwendung nicht aktiviert. Aktivieren Sie entweder ASP.NET-Kompatibilität in der Web.config-Datei, oder legen Sie die AspNetCompatibilityRequirementsAttribute.AspNetCompatibility-Eigenschaft fest.|
