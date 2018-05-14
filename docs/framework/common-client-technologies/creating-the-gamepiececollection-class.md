---
title: Erstellen der GamePieceCollection-Klasse
ms.date: 03/30/2017
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
ms.openlocfilehash: 6473f7afce1422ee31d4f1872f8310bdeeb9a3b6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-the-gamepiececollection-class"></a>Erstellen der GamePieceCollection-Klasse
Die **GamePieceCollection**-Klasse wird von der generischen List-Klasse abgeleitet und stellt Methoden zum einfachen Verwalten von mehreren **GamePiece**-Objekten bereit.  
  
## <a name="creating-the-code"></a>Erstellen des Codes  
 Der Konstruktor der **GamePieceCollection**-Klasse initialisiert den privaten Member *capturedIndex*. Dieses Feld wird zur Nachverfolgung verwendet, welche Spielelemente aktuell über die Mausaufzeichnung verfügen.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 Die Methoden **ProcessInertia** und **Draw** vereinfachen den in den Spielmethoden [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) und [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) benötigten Code, indem sie alle Spielelemente in einer Auflistung aufzählt und die jeweilige Methode auf jedem **GamePiece**-Objekt aufrufen.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 Die **UpdateFromMouse**-Methode wird auch während der Spielaktualisierung aufgerufen. Sie weist nur einem Spielelement die Mausaufzeichnung zu, indem zunächst geprüft wird, ob die aktuelle Aufzeichnung weiterhin aktiv ist (sofern vorhanden). Ist dies der Fall, dürfen keine andere Elemente für die Erfassung überprüft werden.  
  
 Wenn aktuell kein Element über die Erfassung verfügt, zählt die **UpdateFromMouse**-Methode jedes Spielsteins (vom letzten zum ersten) auf und prüft, ob dieser Stein eine Mauserfassung meldet. In diesem Fall wird dieses Element zum aktuell aufgezeichneten Element und es erfolgt keine weitere Verarbeitung. Die **UpdateFromMouse**-Methode überprüft zunächst das letzte Element in der Auflistung, damit bei sich überlappenden Elementen das Element mit der höheren Z-Reihenfolge die Erfassung erhält. Die Z-Reihenfolge ist weder explizit noch änderbar. Sie wird einfach durch die Reihenfolge bestimmt, in der Spielelemente zur Auflistung hinzugefügt werden.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a>Siehe auch  
 [Manipulationen und Trägheit](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Erstellen der GamePiece-Klasse](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Erstellen der Game1-Klasse](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [Vollständige Codeauflistungen](../../../docs/framework/common-client-technologies/full-code-listings.md)
