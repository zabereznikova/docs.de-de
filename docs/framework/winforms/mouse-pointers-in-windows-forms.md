---
title: Mauszeiger in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fb0e193ccbced719f30ede91cb59cd51dd349a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mouse-pointers-in-windows-forms"></a>Mauszeiger in Windows Forms
Die Maus *Zeiger*, die manchmal als des Cursors bezeichnet ist eine Bitmap, die einen Fokuspunkt gibt an, auf dem Bildschirm für Benutzereingaben mit der Maus. Dieses Thema bietet einen Überblick über der Mauszeiger in Windows Forms und beschreibt einige der Methoden zum Ändern und Steuern der Mauszeiger die Form.  
  
## <a name="accessing-the-mouse-pointer"></a>Zugreifen auf den Mauszeiger  
 Der Mauszeiger die Form dargestellte der <xref:System.Windows.Forms.Cursor> -Klasse, und jedes <xref:System.Windows.Forms.Control> verfügt über eine <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> Eigenschaft, die den Zeiger für das Steuerelement angibt. Die <xref:System.Windows.Forms.Cursor> Klasse enthält Eigenschaften, die den Zeiger wird, wie z. B. beschrieben die <xref:System.Windows.Forms.Cursor.Position%2A> und <xref:System.Windows.Forms.Cursor.HotSpot%2A> Eigenschaften und Methoden, wie z. B. die Darstellung des Zeigers ändern können, die <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, und <xref:System.Windows.Forms.Cursor.DrawStretched%2A> Methoden.  
  
## <a name="controlling-the-mouse-pointer"></a>Steuern des Mauszeigers  
 In einigen Fällen empfiehlt es sich um den Bereich, in dem der Mauszeiger die Form kann verwendet werden, oder Ändern der Position der Maus, zu beschränken. Sie können abrufen oder festlegen die aktuelle Position der Maus mithilfe der <xref:System.Windows.Forms.Cursor.Position%2A> Eigenschaft der <xref:System.Windows.Forms.Cursor>. Darüber hinaus können Sie den Bereich der Mauszeiger die Form genutzt werden beschränken Einstellung werden die <xref:System.Windows.Forms.Cursor.Clip%2A> Eigenschaft. Clipbereich, wird standardmäßig ist den gesamten Bildschirm.  
  
## <a name="changing-the-mouse-pointer"></a>Ändern des Mauszeigers  
 Ändern des Mauszeigers ist eine wichtige Möglichkeit zum Bereitstellen von Feedback für den Benutzer. Beispielsweise kann der Mauszeiger die Form geändert werden, in die Handler die <xref:System.Windows.Forms.Control.MouseEnter> und <xref:System.Windows.Forms.Control.MouseLeave> Ereignisse, die dem Benutzer zu informieren, dass Berechnungen ausgeführt werden und eine Benutzerinteraktion in das Steuerelement zu begrenzen. In einigen Fällen ändert sich der Mauszeiger aufgrund Systemereignisse, z. B. wenn die Anwendung in einem Drag & Drop-Vorgang einbezogen ist.  
  
 Die primäre Methode zum Ändern des Mauszeigers wird durch Festlegen der <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.Control.DefaultCursor%2A> Eigenschaft eines Steuerelements zu einer neuen <xref:System.Windows.Forms.Cursor>. Beispiele für Ändern des Mauszeigers finden Sie im Codebeispiel in die <xref:System.Windows.Forms.Cursor> Klasse. Darüber hinaus die <xref:System.Windows.Forms.Cursors> Klasse macht eine Reihe von <xref:System.Windows.Forms.Cursor> Objekte für viele verschiedene Arten von Zeigern, z. B. ein Zeiger, der einer Hand ähnelt. Um den Wartevorgang Zeiger anzuzeigen, die eine Sanduhr angezeigt, ähnelt, wenn der Mauszeiger auf dem Steuerelement befindet, verwenden die <xref:System.Windows.Forms.Control.UseWaitCursor%2A> Eigenschaft von der <xref:System.Windows.Forms.Control> Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Cursor>  
 [Mauseingabe in einer Windows Forms-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Drag & Drop-Funktionen in Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
