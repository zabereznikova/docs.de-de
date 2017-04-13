---
title: "Gewusst wie: Ermitteln der gedr&#252;ckten Modifizierertaste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ALT-TASTEN"
  - "STRG-Tasten"
  - "Ereignisse [Windows Forms], Tastatur"
  - "Ereignisse [Windows Forms], Maus"
  - "Tastatureingabe"
  - "Tastaturen, Tastatureingabe"
  - "Schlüssel, ALT-TASTEN"
  - "Schlüssel, STRG-Tasten"
  - "Schlüssel, Ermitteln von zuletzt gedrückten"
  - "Schlüssel, Modifizierertasten"
  - "Schlüssel, UMSCHALT-TASTEN"
  - "Keys.Alt-Enumerationsmember"
  - "Keys.ControlKey-Enumerationsmember"
  - "Keys.Shift-Enumerationsmember"
  - "Modifizierertasten"
  - "UMSCHALT-TASTEN"
  - "Benutzereingabe, Überprüfen der Tastatur"
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Ermitteln der gedr&#252;ckten Modifizierertaste
Beim Erstellen einer Anwendung, die über Tastatureingaben gesteuert werden kann, sollten Sie eine Überwachung der Modifizierertasten \(z. B. UMSCHALT\-, ALT\- und STRG\-TASTEN\) einrichten.  Wenn eine Modifizierertaste in Verbindung mit anderen Tasten oder Mausklicks gedrückt wird, kann die Anwendung entsprechend darauf reagieren.  Wenn beispielsweise der Buchstabe S gedrückt wird, wird auf dem Bildschirm lediglich ein "s" angezeigt, wenn aber die Tasten STRG\+S gedrückt werden, wird das aktuelle Dokument gespeichert.  Wenn Sie das <xref:System.Windows.Forms.Control.KeyDown>\-Ereignis behandeln, legt die <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A>\-Eigenschaft des vom Ereignishandler empfangenen <xref:System.Windows.Forms.KeyEventArgs> fest, welche Modifizierertasten gedrückt werden.  Alternativ legt die <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>\-Eigenschaft des <xref:System.Windows.Forms.KeyEventArgs> das gedrückte Zeichen sowie weitere Modifizierertasten fest, die mit einem bitweisen Operator OR kombiniert werden.  Wenn Sie jedoch das <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis oder ein Mausereignis behandeln, empfängt der Ereignishandler diese Informationen nicht.  In diesem Fall müssen Sie die <xref:System.Windows.Forms.Control.ModifierKeys%2A>\-Eigenschaft der <xref:System.Windows.Forms.Control>\-Klasse verwenden.  Grundsätzlich müssen Sie einen bitweisen Operator AND des entsprechenden <xref:System.Windows.Forms.Keys>\-Werts und des getesteten Werts ausführen.  Die <xref:System.Windows.Forms.Keys>\-Enumeration ermöglicht Varianten der einzelnen Modifizierertasten. Daher ist es wichtig, dass Sie den bitweisen Operator AND mit dem richtigen Wert ausführen.  Die UMSCHALTTASTE wird beispielsweise durch <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys> und <xref:System.Windows.Forms.Keys> dargestellt. Der richtige Wert zum Testen der UMSCHALTTASTE als Modifizierertaste ist <xref:System.Windows.Forms.Keys>.  Zum Testen von STRG und ALT als Modifizierertasten sollten Sie dementsprechend den Wert <xref:System.Windows.Forms.Keys> bzw. den Wert <xref:System.Windows.Forms.Keys> verwenden.  
  
> [!NOTE]
>  Visual Basic\-Programmierer können Tasteninformationen auch über die <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>\-Eigenschaft aufrufen.  
  
### So ermitteln Sie, welche Modifizierertaste gedrückt wurde  
  
-   Verwenden Sie den bitweisen Operator `AND` mit der <xref:System.Windows.Forms.Control.ModifierKeys%2A>\-Eigenschaft und einem Wert der <xref:System.Windows.Forms.Keys>\-Enumeration, um zu bestimmen, ob eine bestimmte Modifizierertaste gedrückt wird.  Im folgenden Codebeispiel wird veranschaulicht, wie Sie bestimmen, ob die UMSCHALTTASTE innerhalb eines <xref:System.Windows.Forms.Control.KeyPress>\-Ereignishandlers gedrückt wird.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>   
 [Tastatureingaben in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How to: Determine If CapsLock is On in Visual Basic](http://msdn.microsoft.com/de-de/91e60f5c-dd61-4222-ba5f-39af803afd8c)