---
title: "Transaktionsmodelle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Transaktionsmodelle
In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.  
  
 Beim Einsatz von Transaktionen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist es wichtig zu verstehen, dass keine Entscheidung zwischen verschiedenen Transaktionsmodellen getroffen wird, sondern eher auf verschiedenen Schichten eines integrierten und konsistenten Modells gearbeitet wird.  
  
 In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.  
  
## Windows Communication Foundation\-Transaktionen  
 Die Transaktionsunterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht das Schreiben von Transaktionsdiensten.Zusätzlich können Anwendungen durch die Unterstützung des WS\-AtomicTransaction \(WS\-AT\)\-Protokolls Transaktionen an Webdienste übertragen, die entweder über [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oder die Technologie von Fremdanbietern erstellt wurden.  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten oder \-Anwendungen bieten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Transaktionsfunktionen Attribute und die Konfiguration für eine deklarative Angabe, wie und wann die Infrastruktur Transaktionen erstellen, übermitteln oder synchronisieren sollte.  
  
## System.Transactions\-Transaktionen  
 Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zum Erstellen von Transaktionsanwendungen mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](http://go.microsoft.com/fwlink/?LinkId=94947) \(möglicherweise in englischer Sprache\).  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten oder \-Anwendungen bietet <xref:System.Transactions> das Programmiermodell für das Erstellen von Transaktionen im Rahmen einer Clientanwendung und, bei Bedarf, für die spezielle Interaktion mit einer Transaktion in einem Dienst.  
  
## MSDTC\-Transaktionen  
 Der Microsoft Distributed Transaction Coordinator \(MSDTC\) ist ein Transaktions\-Manager, der verteilte Transaktionen unterstützt.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [DTC\-Programmierreferenz](http://go.microsoft.com/fwlink/?LinkId=94948) \(möglicherweise in englischer Sprache\).  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten oder \-Anwendungen bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt wurden.