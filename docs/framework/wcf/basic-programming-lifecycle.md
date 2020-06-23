---
title: Grundlegender Programmierlebenszyklus
description: Erfahren Sie mehr über die Aufgaben zum Erstellen einer WCF-Anwendung. WCF ermöglicht Apps die Kommunikation auf demselben Computer, über Netzwerke oder auf verschiedenen Anwendungsplattformen.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: c672827fff780fd263f5355520bb6ccf02bb902e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245530"
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
  
## <a name="see-also"></a>Weitere Informationen

- [Implementieren von Dienstverträgen](implementing-service-contracts.md)
