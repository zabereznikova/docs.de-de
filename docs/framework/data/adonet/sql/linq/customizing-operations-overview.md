---
title: 'Anpassen von Vorgängen: Übersicht'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 29fb75271b7bc324d462078e94e4a28534986fba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075976"
---
# <a name="customizing-operations-overview"></a>Anpassen von Vorgängen: Übersicht
Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL für Insert-, Update und Delete-Operationen auf Grundlage der Zuordnung. In der Praxis möchten Sie jedoch in der Regel Ihre eigene Geschäftslogik hinzufügen, um Sicherheit, Validierung etc. zu ermöglichen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] folgende: Methoden zur Anpassung dieser Operationen  
  
## <a name="loading-options"></a>Ladeoptionen  
 In Ihren Abfragen können Sie kontrollieren, wie viele Daten zum Hauptziel abgerufen werden, wenn Sie eine Verbindung zur Datenbank herstellen. Diese Funktionalität wird zum größten Teil durch Verwendung von <xref:System.Data.Linq.DataLoadOptions> implementiert. Weitere Informationen finden Sie unter [verzögertes im Vergleich zu den sofortigen Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Partielle Methoden  
 In seiner Standardzuordnung stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] partielle Methoden bereit, um Sie bei der Implementierung der Geschäftslogik zu unterstützen. Weitere Informationen finden Sie unter [hinzufügen Business Logik mithilfe von partiellen Methoden](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Gespeicherte Prozeduren und benutzerdefinierte Funktionen  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die Verwendung von gespeicherten Prozeduren und benutzerdefinierte Funktionen. Gespeicherte Prozeduren werden häufig verwendet, um Operationen anzupassen. Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Siehe auch

- [Anpassen von Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
