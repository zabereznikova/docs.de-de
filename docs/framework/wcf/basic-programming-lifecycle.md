---
title: Grundlegender Programmierlebenszyklus
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: fe578ba3c655c9c9ea8398b9b2e4d4f974153c8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320816"
---
# <a name="basic-programming-lifecycle"></a>Grundlegender Programmierlebenszyklus
Mit Windows Communication Foundation (WCF) können Anwendungen kommunizieren, ob Sie sich auf demselben Computer, über das Internet oder auf verschiedenen Anwendungsplattformen befinden. In diesem Thema werden die Aufgaben erläutert, die zum Erstellen einer WCF-Anwendung erforderlich sind. Eine funktionierende Beispielanwendung finden Sie unter [Getting Started Tutorial](getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Grundlegende Aufgaben  
 Die folgenden grundlegenden Aufgaben müssen in der angegebenen Reihenfolge ausgeführt werden:  
  
1. Definieren Sie den Dienstvertrag. Ein Dienstvertrag gibt die Signatur eines Diensts, die Daten, die ausgetauscht werden, sowie andere vertraglich erforderliche Daten an. Weitere Informationen finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md).  
  
2. Implementieren Sie den Vertrag. Zum Implementieren eines Dienstvertrags erstellen Sie eine Klasse, die den Vertrag implementiert, und geben Sie das benutzerdefinierte Verhalten der Laufzeit an. Weitere Informationen finden Sie unter [Implementieren von Dienstverträgen](implementing-service-contracts.md).  
  
3. Konfigurieren Sie den Dienst, indem Sie Endpunkte und andere Verhaltensinformationen angeben. Weitere Informationen finden Sie unter [Konfigurieren von Diensten](configuring-services.md).  
  
4. Hosten Sie den Dienst. Weitere Informationen finden Sie unter [Hostingdienste](hosting-services.md).  
  
5. Erstellen Sie eine Clientanwendung. Weitere Informationen finden Sie unter [Building Clients](building-clients.md).  
  
 Obwohl die Themen in diesem Abschnitt dieser Reihenfolge entsprechen, beginnen einige Szenarien nicht am Anfang. Wenn Sie beispielsweise einen Client für einen bereits vorhandenen Dienst erstellen möchten, beginnen Sie bei Schritt 5. Wenn Sie hingegen einen Dienst erstellen, den andere verwenden, können Sie Schritt 5 überspringen.  
  
 Wenn Sie mit der Entwicklung von Dienstverträgen vertraut sind, können Sie auch [die Einführung in die Erweiterbarkeit](introduction-to-extensibility.md)lesen. Wenn Sie Probleme mit Ihrem Dienst haben, überprüfen Sie den [Schnellstart zur Problem](wcf-troubleshooting-quickstart.md) Behandlung von WCF, um festzustellen, ob andere Probleme dieselben oder ähnliche Probleme haben.  
  
## <a name="see-also"></a>Siehe auch

- [Implementieren von Dienstverträgen](implementing-service-contracts.md)
