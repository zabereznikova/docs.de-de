---
title: Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 78deee127f43aac71a1a4daaab808598065c2fe5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung
Dieser Artikel beschreibt, wie Sie Manipulationen und Trägheitsverarbeitung in einer Microsoft XNA-Anwendung verwenden können, um die Bewegungen von Spielelementen zu steuern. Bevor Sie diesen Artikel lesen, sollten Sie sich mit dem Thema [Manipulationen und Trägheit (Übersicht)](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) sowie mit den grundlegenden XNA-Programmierkonzepten vertraut gemacht haben.  
  
 Um die in diesem Artikel beschriebenen Aufgaben durchführen zu können, muss Ihr XNA-Projekt auf die <xref:System.Windows.Input.Manipulations>-Assembly verweisen, und [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([Herunterladen](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) muss auf Ihrem Computer installiert sein, damit Ihr Projekt auf XNA-Assemblys verweisen kann.  
  
## <a name="overview-of-functionality"></a>Funktionen im Überblick  
 In diesem Artikel wird gezeigt, wie Sie eine benutzerdefinierte Klasse erstellen, die ein Spielelement darstellt, das Manipulation und Trägheitsverarbeitung verwendet. Diese Klasse ermöglicht das Manipulieren eines Spielelements auf dem Bildschirm, indem es mit der Maus gezogen und die Maustaste dann losgelassen wird. Sobald die Maustaste losgelassen wurde, bewegt die Trägheitsverarbeitung das Spielelement weiter, während es nach und nach langsamer wird. Die Bewegung ist linear und winklig.  
  
 ![Eine einfache Anwendung mit Manipulationen und Trägheit](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GmeXna")  
  
 Darüber hinaus wird eine benutzerdefinierte Auflistung erstellt, die mehrere Spielelemente verwaltet. Dies vereinfacht die Verarbeitung, die für die XNA Game-Klasse erforderlich ist.  
  
 [Erstellen der GamePiece-Klasse](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Erstellen der GamePieceCollection-Klasse](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Erstellen der Game1-Klasse](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Vollständige Codeauflistungen](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Input.Manipulations>  
 [Überblick über Manipulationen und Trägheit](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
