---
title: 'Anpassen von Vorgängen: Übersicht'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: d4d375716e3199afcbbb9bbd8b8b04867ca0e5fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173522"
---
# <a name="customizing-operations-overview"></a>Anpassen von Vorgängen: Übersicht

Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL für Insert-, Update und Delete-Operationen auf Grundlage der Zuordnung. In der Praxis möchten Sie jedoch in der Regel Ihre eigene Geschäftslogik hinzufügen, um Sicherheit, Validierung etc. zu ermöglichen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu den Techniken, mit denen diese Vorgänge angepasst werden, gehören die folgenden.  
  
## <a name="loading-options"></a>Ladeoptionen  

 In Ihren Abfragen können Sie kontrollieren, wie viele Daten zum Hauptziel abgerufen werden, wenn Sie eine Verbindung zur Datenbank herstellen. Diese Funktionalität wird zum größten Teil durch Verwendung von <xref:System.Data.Linq.DataLoadOptions> implementiert. Weitere Informationen finden Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Partielle Methoden  

 In seiner Standardzuordnung stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] partielle Methoden bereit, um Sie bei der Implementierung der Geschäftslogik zu unterstützen. Weitere Informationen finden Sie unter [Hinzufügen von Geschäftslogik mithilfe von partiellen Methoden](adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Gespeicherte Prozeduren und benutzerdefinierte Funktionen  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die Verwendung von gespeicherten Prozeduren und benutzerdefinierten Funktionen. Gespeicherte Prozeduren werden häufig verwendet, um Operationen anzupassen. Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](stored-procedures.md).  
  
## <a name="see-also"></a>Siehe auch

- [Anpassen von Insert-, Update- und Delete-Operationen](customizing-insert-update-and-delete-operations.md)
