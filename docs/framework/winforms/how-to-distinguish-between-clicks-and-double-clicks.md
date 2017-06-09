---
title: "Gewusst wie: Unterscheiden zwischen Klicks und Doppelklicks | Microsoft Docs"
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
  - "Klicken mit der Maus, Einfaches Klicken im Vergleich zum Doppelklicken"
  - "Maus, Klick"
  - "Maus, Doppelklick"
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Unterscheiden zwischen Klicks und Doppelklicks
Normalerweise wird mit einem einzigen *Klick* eine Benutzerschnittstellenaktion initiiert, und mit einem *Doppelklick* wird die Aktion erweitert.  So wird mit einem einzigen Klick ein Element markiert, und mit einem Doppelklick wird das ausgewählte Element bearbeitet.  Allerdings lassen sich die Windows Forms\-Klickereignisse nicht so einfach an ein Szenario anpassen, in dem ein Klick und ein Doppelklick inkompatible Aktionen ausführen, da eine Aktion, die mit dem <xref:System.Windows.Forms.Control.Click>\- oder <xref:System.Windows.Forms.Control.MouseClick>\-Ereignis verknüpft ist, ausgeführt wird, bevor die mit dem <xref:System.Windows.Forms.Control.DoubleClick>\- oder <xref:System.Windows.Forms.Control.MouseDoubleClick>\-Ereignis verknüpfte Aktion ausgeführt wird.  In diesem Thema werden zwei Lösungen für dieses Problem erörtert.  Eine Lösung besteht darin, das Doppelklickereignis zu behandeln und ein Rollback der Aktionen in der Behandlung des Klickereignisses zu initiieren.  In selten Fällen müssen Sie ggf. das Klick\- und Doppelklickverhalten simulieren, indem Sie das <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis behandeln und dabei die Eigenschaften <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> und <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> der <xref:System.Windows.Forms.SystemInformation>\-Klasse verwenden.  Sie messen die Zeit zwischen den Klicks, und wenn ein zweiter Klick erfolgt, bevor der Wert von <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> erreicht wurde und der Klick innerhalb des von <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> definierten Rechtecks erfolgt ist, führen Sie die Doppelklickaktion aus, andernfalls führen Sie die Klickaktion aus.  
  
### So führen Sie ein Rollback einer Klickaktion durch  
  
-   Vergewissern Sie sich, dass das Steuerelement, mit dem Sie arbeiten, über das standardmäßig Doppelklickverhalten verfügt.  Andernfalls aktivieren Sie das Steuerelement mit der <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode.  Behandeln Sie das Doppelklickereignis, und führen Sie ein Rollback der Klickaktion und der Doppelklickaktion durch.  Im folgenden Codebeispiel wird gezeigt, wie eine benutzerdefinierte Schaltfläche mit aktiviertem Doppelklick erstellt und wie ein Rollback der Klickaktion im Behandlungscode des Doppelklickereignisses initiiert wird.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### So unterscheiden Sie zwischen Klicks im MouseDown\-Ereignis  
  
-   Behandeln Sie das <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis, und ermitteln Sie die Position und die Zeitspanne zwischen Klicks mit den geeigneten <xref:System.Windows.Forms.SystemInformation>\-Eigenschaften und einer <xref:System.Windows.Forms.Timer>\-Komponente.  Machen Sie die geeignete Aktion davon abhängig, ob ein Klick oder ein Doppelklick stattfindet.  Das folgende Codebeispiel veranschaulicht, wie Sie dabei vorgehen.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieser Beispiele über die Befehlszeile für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)