---
title: Mauszeiger in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: e9b572ba40618a72b8db58917008ebd61a23de79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800776"
---
# <a name="mouse-pointers-in-windows-forms"></a>Mauszeiger in Windows Forms
Die Maus *Zeiger*, der als der Cursor, bezeichnet wird eine Bitmap, die auf dem Bildschirm für die Benutzereingabe mit der Maus einen Fokuspunkt festlegt wird. Dieses Thema bietet einen Überblick über der Mauszeiger in Windows Forms und beschreibt einige der Möglichkeiten, ändern und steuern den Mauszeiger auf.  
  
## <a name="accessing-the-mouse-pointer"></a>Zugreifen auf den Mauszeiger  
 Der Mauszeiger wird dargestellt, durch die <xref:System.Windows.Forms.Cursor> -Klasse, und jedes <xref:System.Windows.Forms.Control> verfügt über eine <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> Eigenschaft, die den Zeiger für das Steuerelement angibt. Die <xref:System.Windows.Forms.Cursor> Klasse enthält Eigenschaften, die beschreiben, die Zeiger ist, z. B. die <xref:System.Windows.Forms.Cursor.Position%2A> und <xref:System.Windows.Forms.Cursor.HotSpot%2A> Eigenschaften und Methoden, die die Darstellung des Zeigers ändern können, wie z.B. die <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, und <xref:System.Windows.Forms.Cursor.DrawStretched%2A> -Methoden.  
  
## <a name="controlling-the-mouse-pointer"></a>Steuern des Mauszeigers  
 In einigen Fällen empfiehlt es sich um den Bereich, in dem der Mauszeiger kann verwendet werden, oder Ändern der Position der Maus, zu beschränken. Können Sie abrufen oder festlegen die aktuelle Position der Maus mithilfe der <xref:System.Windows.Forms.Cursor.Position%2A> Eigenschaft der <xref:System.Windows.Forms.Cursor>. Darüber hinaus können Sie einschränken, den Bereich der Mauszeiger verwendet werden kann Einstellung werden die <xref:System.Windows.Forms.Cursor.Clip%2A> Eigenschaft. Der Clipbereich, in der Standardeinstellung ist der gesamte Bildschirm.  
  
## <a name="changing-the-mouse-pointer"></a>Ändern des Mauszeigers  
 Ändern des Mauszeigers ist eine wichtige Möglichkeit zum Senden von Feedback an den Benutzer. Beispielsweise kann der Mauszeiger geändert werden, in der Handler für die <xref:System.Windows.Forms.Control.MouseEnter> und <xref:System.Windows.Forms.Control.MouseLeave> Ereignisse, die dem Benutzer mitzuteilen, dass Berechnungen durchgeführt werden und eine Benutzerinteraktion in das Steuerelement zu beschränken. In einigen Fällen ändert sich der Mauszeiger aufgrund von Systemereignissen, z. B. wenn die Anwendung in einem Drag & Drop-Vorgang beteiligt ist.  
  
 Der einfachste Weg zum Ändern des Mauszeigers wird durch Festlegen der <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.Control.DefaultCursor%2A> Eigenschaft eines Steuerelements zu einem neuen <xref:System.Windows.Forms.Cursor>. Beispiele für Ändern des Mauszeigers, finden Sie im Codebeispiel in die <xref:System.Windows.Forms.Cursor> Klasse. Darüber hinaus die <xref:System.Windows.Forms.Cursors> Klasse macht eine Reihe von <xref:System.Windows.Forms.Cursor> Objekte für viele verschiedene Arten von Zeigern, z. B. ein Zeiger, der einer Hand ähnelt. Um die Wait-Zeiger ist, anzuzeigen, der eine Sanduhr angezeigt, wie es aussieht, wenn der Mauszeiger auf dem Steuerelement befindet, verwenden Sie die <xref:System.Windows.Forms.Control.UseWaitCursor%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Cursor>
- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)
- [Drag & Drop-Funktionen in Windows Forms](drag-and-drop-functionality-in-windows-forms.md)
