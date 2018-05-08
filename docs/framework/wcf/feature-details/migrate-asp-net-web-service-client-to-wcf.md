---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation
Das folgende Verfahren beschreibt die folgenden Schritte aus, die ausgeführt werden, um den Clientcode ASP.NET-Webdienst zu WCF migrieren möchten.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>So migrieren Sie ASP.NET-Webdienst-Clientcode zu WCF  
  
1.  Stellen Sie sicher, dass für den Client ein umfassender Satz an Tests vorhanden ist.  
  
2.  Verwenden Sie Visual Studio 2005, um ein Upgrade der Clientanwendung auf .NET 2.0 durchzuführen. Führen Sie die Tests aus.  
  
3.  Entfernen Sie ASP.NET-Clientcode aus dem Clientprojekt. Dieser Code wird mithilfe des WSDL.exe-Tools in Modulen generiert.  
  
4.  Generieren Sie WCF Client Code mit der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Fügen Sie diesen Code zum Clientprojekt hinzu, und fügen Sie die Konfigurationsausgabe in die bestehende Konfigurationsdatei des Clients ein.  
  
5.  Kompilieren Sie die Anwendung. Reparieren Sie die Kompilierungsfehler, indem Sie Verweise auf ehemaligen ASP.NET-Clienttypen durch Verweise auf die neuen WCF-Clienttypen ersetzen.  
  
6.  Führen Sie die Tests aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
