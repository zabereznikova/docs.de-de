---
title: "Anpassen von Operationen: Übersicht"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7653ca137c93da5174e0ddcd1ced8bdfceaa9edc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-operations-overview"></a>Anpassen von Operationen: Übersicht
Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL für Insert-, Update und Delete-Operationen auf Grundlage der Zuordnung. In der Praxis möchten Sie jedoch in der Regel Ihre eigene Geschäftslogik hinzufügen, um Sicherheit, Validierung etc. zu ermöglichen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Techniken zur Anpassung dieser Operationen zählen den folgende:  
  
## <a name="loading-options"></a>Ladeoptionen  
 In Ihren Abfragen können Sie kontrollieren, wie viele Daten zum Hauptziel abgerufen werden, wenn Sie eine Verbindung zur Datenbank herstellen. Diese Funktionalität wird zum größten Teil durch Verwendung von <xref:System.Data.Linq.DataLoadOptions> implementiert. Weitere Informationen finden Sie unter [verzögerte und sofortige laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Partielle Methoden  
 In seiner Standardzuordnung stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] partielle Methoden bereit, um Sie bei der Implementierung der Geschäftslogik zu unterstützen. Weitere Informationen finden Sie unter [hinzufügen Business Logik von mithilfe von partiellen Methoden](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Gespeicherte Prozeduren und benutzerdefinierte Funktionen  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]unterstützt die Verwendung von gespeicherten Prozeduren und benutzerdefinierte Funktionen. Gespeicherte Prozeduren werden häufig verwendet, um Operationen anzupassen. Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von INSERT-, Update- und Löschvorgänge](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
