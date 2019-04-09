---
title: Grundlegender Programmierlebenszyklus
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: 32586ad3ec62630e6abafd33b385788c20155b28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178489"
---
# <a name="basic-programming-lifecycle"></a>Grundlegender Programmierlebenszyklus
Windows Communication Foundation (WCF) ermöglicht Anwendungen das kommunizieren, ob diese auf demselben Computer ausführen, über das Internet oder auf verschiedenen Anwendungsplattformen sind. Dieses Thema beschreibt die Aufgaben, die zum Erstellen einer WCF-Anwendung erforderlich sind. Eine funktionierende beispielanwendung finden Sie unter [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Grundlegende Aufgaben  
 Die folgenden grundlegenden Aufgaben müssen in der angegebenen Reihenfolge ausgeführt werden:  
  
1.  Definieren Sie den Dienstvertrag. Ein Dienstvertrag gibt die Signatur eines Diensts, die Daten, die ausgetauscht werden, sowie andere vertraglich erforderliche Daten an. Weitere Informationen finden Sie unter [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementieren Sie den Vertrag. Zum Implementieren eines Dienstvertrags erstellen Sie eine Klasse, die den Vertrag implementiert, und geben Sie das benutzerdefinierte Verhalten der Laufzeit an. Weitere Informationen finden Sie unter [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Konfigurieren Sie den Dienst, indem Sie Endpunkte und andere Verhaltensinformationen angeben. Weitere Informationen finden Sie unter [Configuring Services](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Hosten Sie den Dienst. Weitere Informationen finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Erstellen Sie eine Clientanwendung. Weitere Informationen finden Sie unter [Erstellen von Clients](../../../docs/framework/wcf/building-clients.md).  
  
 Obwohl die Themen in diesem Abschnitt dieser Reihenfolge entsprechen, beginnen einige Szenarien nicht am Anfang. Wenn Sie beispielsweise einen Client für einen bereits vorhandenen Dienst erstellen möchten, beginnen Sie bei Schritt 5. Wenn Sie hingegen einen Dienst erstellen, den andere verwenden, können Sie Schritt 5 überspringen.  
  
 Sobald Sie mit der Entwicklung von Dienstverträgen vertraut sind, lesen Sie bitte auch [Einführung in die Erweiterbarkeit](../../../docs/framework/wcf/introduction-to-extensibility.md). Wenn Sie Probleme mit Ihrem Dienst haben, überprüfen Sie [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) um festzustellen, ob andere die gleichen oder ähnliche Probleme haben.  
  
## <a name="see-also"></a>Siehe auch

- [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
