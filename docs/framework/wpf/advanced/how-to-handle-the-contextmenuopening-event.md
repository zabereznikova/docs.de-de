---
title: "Gewusst wie: Behandeln des ContextMenuOpening -Ereignisses | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ContextMenuOpening-Ereignis"
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Behandeln des ContextMenuOpening -Ereignisses
Das <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Ereignis kann in einer Anwendung so behandelt werden, dass es entweder ein vorhandenes Kontextmenü vor dem Anzeigen anpasst oder das andernfalls angezeigte Menü unterdrückt, indem es die <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Eigenschaft in den Ereignisdaten auf `true` festlegt.  In der Regel wird für <xref:System.Windows.RoutedEventArgs.Handled%2A> der Wert `true` in den Ereignisdaten festgelegt, wenn das Menü vollständig durch ein neues <xref:System.Windows.Controls.ContextMenu>\-Objekt ersetzt werden soll \(dafür ist manchmal das Abbrechen des Vorgangs und das Starten eines neuen Öffnungsvorgangs erforderlich\).  Wenn Sie Handler für das <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Ereignis schreiben, sollten Sie sich der Probleme bei der zeitlichen Steuerung zwischen einem <xref:System.Windows.Controls.ContextMenu>\-Steuerelement und dem Dienst bewusst sein, der zuständig für das Öffnen und Positionieren von Kontextmenüs für Steuerungen im Allgemeinen ist.  In diesem Thema werden einige Codetechniken für verschiedene Szenarien des Öffnens von Kontextmenüs veranschaulicht. Außerdem wird ein Fall dargestellt, in dem die Probleme der zeitlichen Steuerung eine Rolle spielen.  
  
 Es gibt mehrere Szenarien, wie mit dem <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Ereignis umgegangen werden kann:  
  
-   Anpassen der Menüelemente vor dem Anzeigen  
  
-   Ersetzen des gesamten Menüs vor dem Anzeigen  
  
-   Vollständiges Löschen eines vorhandenen Kontextmenüs, sodass kein Kontextmenü angezeigt wird  
  
## Beispiel  
  
## Anpassen der Menüelemente vor dem Anzeigen  
 Das Anpassen der vorhandenen Menüelemente ist recht einfach und wahrscheinlich das häufigste Szenario.  Sie können so vorgehen, um Kontextmenüoptionen hinzuzufügen oder zu entfernen, als Reaktion auf aktuelle Statusinformationen in der Anwendung oder bestimmte Statusinformationen, die als Eigenschaft in dem Objekt verfügbar sind, in dem das Kontextmenü angefordert wird.  
  
 Die allgemeine Vorgehensweise besteht darin, die Quelle des Ereignisses abzurufen, d. h. das spezifische Steuerelement, auf das mit der rechten Maustaste geklickt wurde, und die <xref:System.Windows.FrameworkElement.ContextMenu%2A>\-Eigenschaft daraus abzurufen.  In der Regel wird die <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Auflistung überprüft, um festzustellen, welche Kontextmenüelemente in dem Menü bereits vorhanden sind, und anschließend werden geeignete neue <xref:System.Windows.Controls.MenuItem>\-Elemente der Auflistung hinzugefügt bzw. daraus entfernt.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## Ersetzen des gesamten Menüs vor dem Anzeigen  
 Alternativ dazu ist es auch möglich, das gesamte Kontextmenü zu ersetzen.  Dazu könnten Sie natürlich auch eine Abwandlung des vorherigen Codes verwenden, alle Elemente eines vorhandenen Kontextmenüs entfernen und komplett neue Elemente hinzufügen.  Die intuitivere Vorgehensweise zum Ersetzen aller Elemente im Kontextmenü besteht jedoch darin, ein neues <xref:System.Windows.Controls.ContextMenu> zu erstellen, dieses mit Elementen zu füllen und anschließend die <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>\-Eigenschaft eines Steuerelements auf das neue <xref:System.Windows.Controls.ContextMenu> festzulegen.  
  
 Im Folgenden wird ein einfacher Handlercode für das Ersetzen eines <xref:System.Windows.Controls.ContextMenu> aufgeführt.  Der Code verweist auf eine benutzerdefinierte `BuildMenu`\-Methode, die abgetrennt wird, weil sie von den Beispielhandlern mehrfach aufgerufen wird.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Wenn Sie jedoch diesen Stil von Handler für <xref:System.Windows.FrameworkElement.ContextMenuOpening> verwenden, kann möglicherweise ein Problem mit der zeitlichen Steuerung auftreten, wenn das Objekt, in dem Sie das <xref:System.Windows.Controls.ContextMenu> festlegen, nicht über ein bereits bestehendes Kontextmenü verfügt.  Wenn ein Benutzer mit der rechten Maustaste auf ein Steuerelement klickt, wird <xref:System.Windows.FrameworkElement.ContextMenuOpening> ausgelöst, auch wenn das vorhandene <xref:System.Windows.Controls.ContextMenu> leer oder NULL ist.  Aber in diesem Fall erscheint das <xref:System.Windows.Controls.ContextMenu>, das Sie im Quellelement festlegen, zu spät, um angezeigt zu werden.  Auch wird, falls der Benutzer ein zweites Mal mit der rechten Maustaste klickt, das neue <xref:System.Windows.Controls.ContextMenu> angezeigt, der Wert ist ungleich NULL, und der Handler ersetzt das Menü und zeigt es ordnungsgemäß an, wenn der Handler ein zweites Mal ausgeführt wird.  Es gibt zwei Lösungen für diese Situation:  
  
1.  Stellen Sie sicher, dass die <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Handler immer mit Steuerelementen ausgeführt werden, für die mindestens ein <xref:System.Windows.Controls.ContextMenu>\-Platzhalter verfügbar ist, der durch den Handlercode ersetzt werden soll.  In diesem Fall können Sie zwar weiterhin den Handler aus dem vorherigen Beispiel verwenden, aber in der Regel weisen Sie ein Platzhalter\-<xref:System.Windows.Controls.ContextMenu> im anfänglichen Markup zu:  
  
     [!code-xml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Angenommen, der anfängliche <xref:System.Windows.Controls.ContextMenu>\-Wert wäre auf Grundlage einer vorläufigen Logik NULL.  Sie können entweder das <xref:System.Windows.Controls.ContextMenu> auf NULL prüfen oder ein Flag in Ihrem Code verwenden, um zu überprüfen, ob Ihr Handler mindestens einmal ausgeführt wurde.  Da Sie annehmen, dass das <xref:System.Windows.Controls.ContextMenu> kurz vor dem Anzeigen steht, legt Ihr Handler dann für <xref:System.Windows.RoutedEventArgs.Handled%2A> den Wert `true` in den Ereignisdaten fest.  Für den <xref:System.Windows.Controls.ContextMenuService>, der für die Kontextmenüanzeige zuständig ist, bedeutet ein `true`\-Wert für <xref:System.Windows.RoutedEventArgs.Handled%2A> in den Ereignisdaten eine Anforderung, das Anzeigen der Kontextmenü\-Steuerelement\-Kombination abzubrechen, die das Ereignis ausgelöst hat.  
  
 Nachdem Sie nun das potenziell verdächtige Kontextmenü unterdrückt haben, ist der nächste Schritt das Bereitstellen eines neuen Menüs und dann das Anzeigen dieses Menüs.  Zum Einrichten des neuen Menüs wird wie beim vorherigen Handler vorgegangen: Sie erstellen ein neues <xref:System.Windows.Controls.ContextMenu> und legen die <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>\-Eigenschaft der Steuerelementquelle dafür fest.  Zusätzlich müssen Sie nun die Anzeige des Kontextmenüs erzwingen, da Sie den ersten Versuch unterdrückt haben.  Um die Anzeige zu erzwingen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=fullName>\-Eigenschaft innerhalb des Handlers auf `true` fest.  Seien Sie vorsichtig, wenn Sie so vorgehen, da durch das Öffnen des Kontextmenüs im Handler das <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Ereignis erneut ausgelöst wird.  Wenn Sie den Handler erneut ausführen, wird er endlos rekursiv.  Daher müssen Sie immer auf `null` prüfen oder ein Flag verwenden, wenn Sie ein Kontextmenü innerhalb eines <xref:System.Windows.FrameworkElement.ContextMenuOpening>\-Ereignishandlers öffnen.  
  
## Löschen eines vorhandenen Kontextmenüs, sodass kein Kontextmenü angezeigt wird  
 Das letzte Szenario, beim dem ein Handler geschrieben wird, der ein Menü völlig unterdrückt, kommt nur selten vor.  Wenn ein bestimmtes Steuerelement in einem Kontextmenü nicht angezeigt werden soll, gibt es wahrscheinlich geeignetere Möglichkeiten, dies sicherzustellen, als das Menü dann zu unterdrücken, wenn es durch einen Benutzer angefordert wird.  Wenn Sie jedoch den Handler verwenden möchten, um ein Kontextmenü zu unterdrücken und nicht anzuzeigen, sollte Ihr Handler einfach für <xref:System.Windows.RoutedEventArgs.Handled%2A> den `true`\-Wert in den Ereignisdaten festlegen.  Der <xref:System.Windows.Controls.ContextMenuService>, der für die Kontextmenüanzeige zuständig ist, prüft die Ereignisdaten des Ereignisses, das er für das Steuerelement ausgelöst hat.  Wenn das Ereignis an irgendeiner Position während der Weiterleitung als <xref:System.Windows.RoutedEventArgs.Handled%2A> gekennzeichnet war, wird die Aktion des Öffnens des Kontextmenüs, die das Ereignis ausgelöst hat, unterdrückt.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>   
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)