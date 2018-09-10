---
title: Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248903"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung
Dieser Artikel beschreibt, wie Sie Manipulationen und Trägheitsverarbeitung in einer Microsoft XNA-Anwendung verwenden können, um die Bewegungen von Spielelementen zu steuern. Bevor Sie diesen Artikel lesen, sollten Sie sich mit dem Thema [Manipulationen und Trägheit (Übersicht)](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) sowie mit den grundlegenden XNA-Programmierkonzepten vertraut gemacht haben.  
  
 Um die in diesem Artikel beschriebenen Aufgaben durchführen zu können, muss Ihr XNA-Projekt auf die <xref:System.Windows.Input.Manipulations>-Assembly verweisen, und [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([Herunterladen](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) muss auf Ihrem Computer installiert sein, damit Ihr Projekt auf XNA-Assemblys verweisen kann.  
  
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
