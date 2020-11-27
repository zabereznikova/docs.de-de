---
title: Übersicht über Windows-Kommunikationfoundation-Transaktionen
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
ms.openlocfilehash: 1486290241fdb40d415278c4a01738aa711e2182
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261474"
---
# <a name="windows-communication-foundation-transactions-overview"></a>Übersicht über Windows-Kommunikationfoundation-Transaktionen

Transaktionen stellen eine Möglichkeit dar, mehrere Aktionen oder Vorgänge in eine einzelne unteilbare Ausführungseinheit zu gruppieren. Eine Transaktion ist eine Auflistung von Vorgängen mit den folgenden Eigenschaften:  
  
- Unteilbarkeit. Dadurch wird sichergestellt, dass entweder alle unter einer bestimmten Transaktion ausgeführten Updates übernommen und dauerhaft gemacht werden oder abgebrochen und in ihren vorherigen Zustand zurückversetzt werden.  
  
- Konsistenz. Dadurch wird sichergestellt, dass die unter einer bestimmten Transaktion vorgenommenen Änderungen eine Transformation von einem konsistenten Zustand zu einem anderen darstellen. Beispielsweise ändert eine Transaktion, bei der Geld von einem Girokonto auf ein Sparkonto überwiesen wird, die Geldmenge auf dem Bankkonto insgesamt nicht.  
  
- Isolation: Dadurch wird verhindert, dass eine Transaktion ausgecheckte Änderungen beobachtet, die zu anderen gleichzeitigen Transaktionen gehören. Isolation bietet eine Abstraktion von Parallelität und stellt gleichzeitig sicher, dass eine Transaktion keine unerwarteten Auswirkungen auf die Ausführung einer anderen Transaktion haben kann.  
  
- Dauerhaftigkeit. Dies bedeutet, dass Updates verwalteter Ressourcen (z. B. eines Datensatzes in einer Datenbank) nach der Ausführung bei Fehlern dauerhaft sind.  
  
 Windows Communication Foundation (WCF) stellt einen umfangreichen Satz von Funktionen bereit, mit denen Sie verteilte Transaktionen in der Webdienst Anwendung erstellen können.  
  
 WCF implementiert die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, das es WCF-Anwendungen ermöglicht, Transaktionen zu interoperablen Anwendungen zu übertragen, z. b. mit einer Technologie von Drittanbietern erstellten interoperablen Webdiensten. WCF implementiert außerdem die Unterstützung für das OLE Transactions-Protokoll, das in Szenarien verwendet werden kann, in denen keine Interop-Funktionalität zum Aktivieren des Transaktions Flusses erforderlich ist.  
  
 Sie können eine Anwendungskonfigurationsdatei verwenden, um Bindungen für das Aktivieren bzw. Deaktivieren des Transaktionsflusses zu konfigurieren sowie das gewünschte Transaktionsprotokoll auf einer Bindung festzulegen. Außerdem können Sie mit der Konfigurationsdatei Transaktionstimeouts auf Dienstebene festlegen. Weitere Informationen finden Sie unter [Aktivieren des Transaktions Flusses](enabling-transaction-flow.md).  
  
 Mithilfe von Transaktionsattributen im <xref:System.ServiceModel>-Namespace können Sie die folgenden Aktionen ausführen:  
  
- Konfigurieren von Transaktionstimeouts und Isolationsstufenfilterung mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut.  
  
- Aktivieren der Transaktionsfunktionalität und Konfigurieren des Transaktionsabschlussverhaltens mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut.  
  
- Verwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und <xref:System.ServiceModel.OperationContractAttribute>-Attributs für eine Vertragsmethode, um den Transaktionsfluss zu erfordern, zuzulassen oder zu verweigern.  
  
 Weitere Informationen finden Sie unter [Service Model Transaction-Attribute](servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [ServiceModel-Transaktionsattribute](servicemodel-transaction-attributes.md)
- [Aktivieren des Transaktionsflusses](enabling-transaction-flow.md)
