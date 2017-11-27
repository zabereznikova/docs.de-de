---
title: Integrieren von COM-Anwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a>Integrieren von COM-Anwendungen
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste können mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker direkt in den vorhandenen Code integriert werden. Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Integrieren von COM-Anwendungen (Übersicht)](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Bietet eine Übersicht über die Hauptbestandteile des Integrationsprozesses.  
  
 [Vorgehensweise: registrieren und konfigurieren ein Dienstmonikers](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Zur Verwendung des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmonikers in einer COM-Anwendung müssen die erforderlichen attributierten Typen bei COM registriert werden. Des Weiteren müssen die COM-Anwendung sowie der Moniker mit der erforderlichen Bindungskonfiguration konfiguriert werden.  
  
 [Vorgehensweise: Verwenden der Windows Communication Foundation-Dienstmonikers ohne Registrierung](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Erläutert, wie Sie die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments oder aus einem WS-MetadataExchange-Endpunkt abrufen.  
  
 [Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Beschreibt das Aufrufen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiels mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-WSDL-Moniker.  
  
 [Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Beschreibt das Aufrufen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiels mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Moniker, der einen MEX-Endpunkt angibt.  
  
 [Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker unterstützt die `IChannelCredentials`-Schnittstelle, die andere Methoden zur Angabe von Kanalanmeldeinformationen ermöglicht.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Siehe auch  
 [Integrieren von COM+-Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
