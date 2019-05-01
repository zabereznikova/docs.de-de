---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050778"
---
# <a name="transaction-models"></a>Transaktionsmodelle
In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.  
  
 Wenn Sie Transaktionen in der Windows Communication Foundation (WCF) verwenden, ist es wichtig zu verstehen, dass Sie sind keine zwischen verschiedenen Transaktionsmodellen getroffen Entscheidung, sondern eher auf verschiedenen Schichten eines integrierten und konsistenten Modells.  
  
 In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows-Kommunikationfoundation-Transaktionen  
 Die transaktionsunterstützung in WCF ermöglicht, dass Sie Schreiben von Transaktionsdiensten. Darüber hinaus können Anwendungen durch die Unterstützung für das Protokoll WS-AtomicTransaction (WS-AT), Transaktionen an Webdienste integriert mit WCF oder Drittanbieter-Technologie fließen.  
  
 In einem WCF-Dienst oder Anwendung geben WCF-Transaktion-Funktionen, Attribute und die Konfiguration für eine deklarative Angabe, wie und wann die Infrastruktur sollte erstellen, flow und Transaktionen zu synchronisieren.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions-Transaktionen  
 Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.  
  
 Weitere Informationen zum Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 In einem WCF-Dienst oder Anwendung <xref:System.Transactions> stellt das Programmiermodell bereit, zum Erstellen von Transaktionen in einer Clientanwendung und für die Interaktion mit einer Transaktion explizit, wenn innerhalb eines Diensts erforderlich.  
  
## <a name="msdtc-transactions"></a>MSDTC-Transaktionen  
 Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.  
  
 Weitere Informationen finden Sie unter den [DTC-Programmierreferenz](https://go.microsoft.com/fwlink/?LinkId=94948).  
  
 In einem WCF-Dienst oder Anwendung bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt.
