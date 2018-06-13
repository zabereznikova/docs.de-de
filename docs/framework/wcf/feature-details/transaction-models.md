---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499023"
---
# <a name="transaction-models"></a>Transaktionsmodelle
In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.  
  
 Wenn Sie Transaktionen in der Windows Communication Foundation (WCF) verwenden, ist es wichtig zu verstehen, dass Sie keine zwischen verschiedenen Entscheidung sind, sondern eher auf verschiedenen Ebenen eines integrierten und konsistenten Modells ausgeführt.  
  
 In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows-Kommunikationfoundation-Transaktionen  
 Die Unterstützung von Transaktionen in WCF ermöglicht, dass das Schreiben von Transaktionsdiensten. Darüber hinaus können Anwendungen durch die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, Transaktionen an Webdienste, die mit WCF oder drittanbietertechnologie erstellten fließen.  
  
 Geben Sie in einem WCF-Dienst oder Anwendung sind WCF-Transaktion-Funktionen Attribute und die Konfiguration für deklarativ angeben, wie und wann die Infrastruktur sollte erstellen, übertragen und Transaktionen zu synchronisieren.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions-Transaktionen  
 Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.  
  
 Weitere Informationen zur Vorgehensweise beim Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](http://go.microsoft.com/fwlink/?LinkId=94947).  
  
 In einem WCF-Dienst oder Anwendung <xref:System.Transactions> stellt das Programmiermodell zum Erstellen von Transaktionen im Rahmen einer Clientanwendung und für die Interaktion mit einer Transaktion explizit, wenn innerhalb eines Diensts erforderlich sind.  
  
## <a name="msdtc-transactions"></a>MSDTC-Transaktionen  
 Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.  
  
 Weitere Informationen finden Sie unter der [DTC-Programmierreferenz](http://go.microsoft.com/fwlink/?LinkId=94948).  
  
 In einem WCF-Dienst oder Anwendung sind bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt wurden.
