---
title: Abrufen von Setupinformationen aus einer Anwendungsdomäne
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c5b43258b3ce501d1302c31a70f51341d3a84d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588037"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a>Abrufen von Setupinformationen aus einer Anwendungsdomäne
Jede Instanz einer Anwendungsdomäne besteht sowohl aus Eigenschaften als auch aus <xref:System.AppDomainSetup>-Informationen. Sie können Setupinformationen aus einer Anwendungsdomäne mit der Klasse <xref:System.AppDomain?displayProperty=nameWithType> abrufen. Diese Klasse stellt mehrere Member zur Verfügung, die Konfigurierungsinformationen zu Anwendungsdomänen abrufen.  
  
 Sie können das Objekt **AppDomainSetup** für die Anwendungsdomäne abfragen, um Setupinformationen zu erhalten, die der Erstellung an die Domäne übergeben wurden.  
  
 Im folgenden Beispiel wird eine neue Anwendungsdomäne erstellt, und anschließend werden mehrere Memberwerte an die Konsole ausgegeben.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 In folgendem Beispielen werden Setupinformationen für die Anwendungsdomäne festgelegt und anschließend abgerufen. Beachten Sie, dass `AppDomain.SetupInformation.ApplicationBase` die Konfigurationsinformationen abruft.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](application-domains.md#programming-with-application-domains)
- [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)
