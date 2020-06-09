---
title: Integrieren von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: dc3bbe0ee72ca5583b1e52a61c914ad866a22a05
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596809"
---
# <a name="integrating-with-com-applications"></a>Integrieren von COM-Anwendungen
Windows Communication Foundation (WCF)-Dienste können mithilfe des WCF-Dienstmonikers direkt in Ihren vorhandenen Code integriert werden. Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die Integration von COM-Anwendungen](integrating-with-com-applications-overview.md)  
 Bietet eine Übersicht über die Hauptbestandteile des Integrationsprozesses.  
  
 [Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers](how-to-register-and-configure-a-service-moniker.md)  
 Um den WCF-Dienstmoniker in einer COM-Anwendung zu verwenden, registrieren Sie die erforderlichen attributierten Typen bei com, und konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungs Konfiguration.  
  
 [Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung](use-the-wcf-service-moniker-without-registration.md)  
 Erläutert, wie Sie die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments oder aus einem WS-MetadataExchange-Endpunkt abrufen.  
  
 [Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Beschreibt, wie ein WCF-Beispiel mit einem WCF-WSDL-Moniker aufgerufen wird.  
  
 [Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Beschreibt, wie ein WCF-Beispiel mit einem WCF-Moniker aufgerufen wird, der einen MEX-Endpunkt angibt.  
  
 [Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit](how-to-specify-channel-security-credentials.md)  
 Der WCF-Dienstmoniker unterstützt die- `IChannelCredentials` Schnittstelle, die eine Reihe alternativer Methoden zum Angeben von Kanal Anmelde Informationen zulässt.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Siehe auch

- [Integration in com+-Anwendungen](integrating-with-com-plus-applications.md)
