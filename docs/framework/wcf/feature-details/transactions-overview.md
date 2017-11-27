---
title: "Übersicht über Windows Communication Foundation-Transaktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2be5e7622c51da37c0f39c12258f50b74483fa53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a>Übersicht über Windows-Kommunikationfoundation-Transaktionen
Transaktionen stellen eine Möglichkeit dar, mehrere Aktionen oder Vorgänge in eine einzelne unteilbare Ausführungseinheit zu gruppieren. Eine Transaktion ist eine Auflistung von Vorgängen mit den folgenden Eigenschaften:  
  
-   Unteilbarkeit. Dadurch wird sichergestellt, dass entweder alle unter einer bestimmten Transaktion ausgeführten Updates übernommen und dauerhaft gemacht werden oder abgebrochen und in ihren vorherigen Zustand zurückversetzt werden.  
  
-   Konsistenz. Dadurch wird sichergestellt, dass die unter einer bestimmten Transaktion vorgenommenen Änderungen eine Transformation von einem konsistenten Zustand zu einem anderen darstellen. Beispielsweise ändert eine Transaktion, bei der Geld von einem Girokonto auf ein Sparkonto überwiesen wird, die Geldmenge auf dem Bankkonto insgesamt nicht.  
  
-   Isolation Dadurch wird verhindert, dass eine Transaktion ungespeicherte Änderungen beobachtet, die zu anderen gleichzeitigen Transaktionen gehören. Isolation bietet eine Abstraktion von Parallelität und stellt gleichzeitig sicher, dass eine Transaktion keine unerwarteten Auswirkungen auf die Ausführung einer anderen Transaktion haben kann.  
  
-   Dauerhaftigkeit. Dies bedeutet, dass Updates verwalteter Ressourcen (z. B. eines Datensatzes in einer Datenbank) nach der Ausführung bei Fehlern dauerhaft sind.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet einen umfangreichen Satz an Funktionen, mit denen Sie verteilte Transaktionen in Ihrer Webdienstanwendung erstellen können.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen Transaktionen zu interoperablen Anwendungen ausführen können, z. B. zu mithilfe von Drittanbietertechnologie erstellten interoperablen Webdiensten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert außerdem die Unterstützung für das OLE Transactions-Protokoll, das in Szenarien verwendet werden kann, in denen keine Interop-Funktionalität zum Aktivieren des Transaktionsflusses erforderlich ist.  
  
 Sie können eine Anwendungskonfigurationsdatei verwenden, um Bindungen für das Aktivieren bzw. Deaktivieren des Transaktionsflusses zu konfigurieren sowie das gewünschte Transaktionsprotokoll auf einer Bindung festzulegen. Außerdem können Sie mit der Konfigurationsdatei Transaktionstimeouts auf Dienstebene festlegen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Aktivieren des Transaktionsflusses](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
 Mithilfe von Transaktionsattributen im <xref:System.ServiceModel>-Namespace können Sie die folgenden Aktionen ausführen:  
  
-   Konfigurieren von Transaktionstimeouts und Isolationsstufenfilterung mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut.  
  
-   Aktivieren der Transaktionsfunktionalität und Konfigurieren des Transaktionsabschlussverhaltens mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut.  
  
-   Verwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und <xref:System.ServiceModel.OperationContractAttribute>-Attributs für eine Vertragsmethode, um den Transaktionsfluss zu erfordern, zuzulassen oder zu verweigern.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ServiceModel-Transaktionsattribute](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel-Transaktionsattribute](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [Aktivieren des Transaktionsflusses](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
