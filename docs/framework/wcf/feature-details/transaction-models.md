---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: d6c78a5342bf19d19308352cddc241f436bfcb3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745322"
---
# <a name="transaction-models"></a>Transaktionsmodelle
In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.  
  
 Bei der Verwendung von Transaktionen in Windows Communication Foundation (WCF) ist es wichtig zu verstehen, dass Sie nicht zwischen unterschiedlichen Transaktions Modellen auswählen, sondern stattdessen auf unterschiedlichen Ebenen eines integrierten und konsistenten Modells arbeiten.  
  
 In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows-Kommunikationfoundation-Transaktionen  
 Die Transaktionsunterstützung in WCF ermöglicht das Schreiben von Transaktions Diensten. Außerdem können Anwendungen mit der Unterstützung des WS-AtomicTransaction (WS-AT)-Protokolls Transaktionen an Webdienste übertragen, die entweder mithilfe von WCF oder von Drittanbieter Technologie erstellt wurden.  
  
 In einem WCF-Dienst oder einer WCF-Anwendung stellen WCF-Transaktions Features Attribute und Konfigurationen bereit, um deklarativ anzugeben, wie und wann die infrastrukturtransaktionen erstellen, Fluss und synchronisieren soll.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions-Transaktionen  
 Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.  
  
 Weitere Informationen zum Erstellen einer Transaktions Anwendung mit diesen beiden Modellen finden Sie unter [Schreiben einer transaktionalen Anwendung](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 In einem WCF-Dienst oder einer WCF-Anwendung stellt <xref:System.Transactions> das Programmiermodell zum Erstellen von Transaktionen in einer Client Anwendung und zur expliziten Interaktion mit einer Transaktion in einem Dienst bereit.  
  
## <a name="msdtc-transactions"></a>MSDTC-Transaktionen  
 Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.  
  
 Weitere Informationen finden Sie in der [DTC-Programmier Referenz](https://docs.microsoft.com/previous-versions/windows/desktop/ms686108(v=vs.85)).  
  
 In einem WCF-Dienst oder einer WCF-Anwendung bietet MSDTC die Infrastruktur für die Koordination von Transaktionen, die in einem Client oder Dienst erstellt werden.
