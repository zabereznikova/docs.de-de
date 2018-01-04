---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baf43f2bfa2175062c57f73e45835c251ac5769e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation
Mit dem folgenden Verfahren werden die Schritte beschrieben, die durchgeführt werden müssen, um ASP.NET-Webdienst-Clientcode zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu migrieren.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>So migrieren Sie ASP.NET-Webdienst-Clientcode zu WCF  
  
1.  Stellen Sie sicher, dass für den Client ein umfassender Satz an Tests vorhanden ist.  
  
2.  Verwenden Sie Visual Studio 2005, um ein Upgrade der Clientanwendung auf .NET 2.0 durchzuführen. Führen Sie die Tests aus.  
  
3.  Entfernen Sie ASP.NET-Clientcode aus dem Clientprojekt. Dieser Code wird mithilfe des WSDL.exe-Tools in Modulen generiert.  
  
4.  Generieren von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientcode der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Fügen Sie diesen Code zum Clientprojekt hinzu, und fügen Sie die Konfigurationsausgabe in die bestehende Konfigurationsdatei des Clients ein.  
  
5.  Kompilieren Sie die Anwendung. Korrigieren Sie die Kompilierungsfehler, indem Sie Verweise auf ehemalige ASP.NET-Clienttypen durch Verweise auf die neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clienttypen ersetzen.  
  
6.  Führen Sie die Tests aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
