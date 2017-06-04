---
title: "Gewusst wie: Programmgesteuertes Drucken von XPS-Dateien | Microsoft Docs"
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
  - "Programmgesteuertes Drucken von XPS-Dateien"
  - "XPS-Dateien, Programmgesteuertes Drucken"
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Programmgesteuertes Drucken von XPS-Dateien
Sie können mit einer Überladung der <xref:System.Printing.PrintQueue.AddJob%2A>\-Methode [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]\-Dateien drucken, ohne einen <xref:System.Windows.Controls.PrintDialog> bzw. überhaupt eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] zu öffnen.  
  
 Sie können [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]\-Dateien auch mit den vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>\- und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>\-Methoden des <xref:System.Windows.Xps.XpsDocumentWriter>\-Elements drucken.  Weitere Informationen hierzu finden Sie unter [Printing an XPS Document](http://msdn.microsoft.com/de-de/849555c8-0c4e-48c0-86bc-a5494c69b36c).  
  
 Eine andere Art, [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] zu drucken, ist die Verwendung der <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>\-Methode oder der <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A>\-Methode des <xref:System.Windows.Controls.PrintDialog>\-Steuerelements.  Weitere Informationen finden Sie unter [Aufrufen eines Druckdialogfelds](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
## Beispiel  
 Im Folgenden finden Sie die wichtigsten Schritte zur Verwendung der dreiparametrigen <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>\-Methode.  Details finden sich im unten stehenden Beispiel.  
  
1.  Stellen Sie fest, ob es sich bei dem Drucker um einen XPSDrv\-Drucker handelt.  \(Weitere Informationen über XPSDrv finden Sie unter [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md).\)  
  
2.  Wenn es sich bei dem Drucker nicht um einen XPSDrv\-Drucker handelt, legen Sie das Apartment des Threads auf Singlethread fest.  
  
3.  Instanziieren Sie einen Druckerserver und ein Druckwarteschlangenobjekt.  
  
4.  Rufen Sie unter Angabe eines Auftragnamens die Methode, die zu druckende Datei und ein <xref:System.Boolean>\-Flag auf, das angibt, ob es sich bei dem Drucker um einen XPSDrv\-Drucker handelt.  
  
 Im folgenden Beispiel wird gezeigt, wie alle [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dateien in einem Verzeichnis als Batch gedruckt werden.  Obwohl der Benutzer von der Anwendung aufgefordert wird, das Verzeichnis anzugeben, benötigt die dreiparametrige <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>\-Methode keine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Sie kann in jedem Codepfad verwendet werden, in dem ein [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dateiname und \-Pfad vorhanden sind, die an sie übergeben werden können.  
  
 Die dreiparametrige <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>\-Überladung von <xref:System.Printing.PrintQueue.AddJob%2A> muss immer dann in einem Singlethreadapartment ausgeführt werden, wenn der <xref:System.Boolean>\-Parameter `false` ist. Dies ist gegeben, wenn kein XPSDrv\-Drucker verwendet wird.  Mehrere Threads sind jedoch der Standardapartmentzustand für [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)].  Dieser Standard muss umgekehrt werden, da im Beispiel kein XPSDrv\-Drucker angenommen wird.  
  
 Es gibt zwei Möglichkeiten, den Standard zu ändern.  Eine Möglichkeit besteht darin, einfach das <xref:System.STAThreadAttribute> \(d. h. "`[System.STAThreadAttribute()]`"\) genau über der ersten Zeile der `Main`\-Methode der Anwendung \(üblicherweise "`static void Main(string[] args)`"\) hinzuzufügen.  Allerdings erfordern viele Anwendungen, dass die `Main`\-Methode über einen Multithread\-Apartmentzustand verfügt, sodass es eine zweite Möglichkeit gibt: Legen Sie den Aufruf von <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> in einem separaten Thread ab, dessen Apartmentzustand mithilfe von <xref:System.Threading.Thread.SetApartmentState%2A> auf <xref:System.Threading.ApartmentState> festgelegt wird.  Im folgenden Beispiel wird dieses zweite Verfahren verwendet.  
  
 Das Beispiel beginnt entsprechend mit der Instanziierung eines <xref:System.Threading.Thread>\-Objekts und der Übergabe einer **PrintXPS**\-Methode als <xref:System.Threading.ThreadStart>\-Parameter.  \(Die **PrintXPS**\-Methode wird später im Beispiel definiert.\) Danach wird der Thread auf ein Singlethreadapartment festgelegt.  Mit dem verbleibenden Code der `Main`\-Methode wird der neue Thread gestartet.  
  
 Der Hauptbestandteil des Beispiels steckt in der `static` **BatchXPSPrinter.PrintXPS**\-Methode.  Nach dem Erstellen eines Druckerservers und einer Druckwarteschlange wird der Benutzer von der Methode aufgefordert, ein Verzeichnis anzugeben, das [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dateien enthält.  Nachdem überprüft wurde, ob das Verzeichnis vorhanden ist und XPS\-Dateien enthält, fügt die Methode der Druckwarteschlange jede dieser Dateien hinzu.  Im Beispiel wird angenommen, dass es sich bei dem Drucker nicht um einen XPSDrv\-Drucker handelt, sodass `false` an den letzten Parameter der <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>\-Methode übergeben wird.  Aus diesem Grund überprüft die Methode das [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Markup in der Datei, bevor sie versucht, es in die Seitenbeschreibungssprache des Druckers umzuwandeln.  Wenn die Validierung fehlschlägt, wird eine Ausnahme ausgelöst.  Im Beispielcode wird die Ausnahme abgefangen, der Benutzer wird darüber benachrichtigt, und anschließend wird die nächste [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Datei verarbeitet.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Wenn Sie einen XPSDrv\-Drucker verwenden, können Sie den abschließenden Parameter auf `true` festlegen.  Da [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] die Seitenbeschreibungssprache des Druckers ist, sendet in diesem Fall die Methode die Datei ohne Überprüfung oder Umwandlung in eine andere Seitenbeschreibungssprache an den Drucker.  Wenn Sie zur Entwurfszeit unsicher sind, ob die Anwendung einen XPSDrv\-Drucker verwendet, können Sie die Anwendung so ändern, dass sie die <xref:System.Printing.PrintQueue.IsXpsDevice%2A>\-Eigenschaft liest, und abhängig vom Ergebnis eine Verzweigung ausführt.  
  
 Da unmittelbar nach der Veröffentlichung von [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] und [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] nur wenige XPSDrv\-Drucker zur Verfügung stehen werden, müssen Sie Nicht\-XPSDrv\-Drucker ggf. als XPSDrv\-Drucker tarnen.  Fügen Sie hierzu auf dem Computer, der die Anwendung ausführt, im folgenden Registrierungsschlüssel die Datei Pipelineconfig.xml zur Liste der Dateien hinzu:  
  
 HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Print\\Environments\\Windows NT x86\\Drivers\\Version\-3\\*\<PseudoXPSPrinter\>*\\DependentFiles  
  
 wobei *\<PseudoXPSPrinter\>* für eine beliebige Druckwarteschlange steht.  Der Computer muss anschließend neu gestartet werden.  
  
 Mithilfe der Tarnung können Sie `true` als abschließenden Parameter von <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> übergeben, ohne eine Ausnahme auszulösen. Das es sich bei *\<PseudoXPSPrinter\>* aber eigentlich nicht um einen XPSDrv\-Drucker handelt, werden Sie keine korrekte Druckerausgabe erhalten.  
  
 **Hinweis** Der Einfachkeit halber gilt im oben stehenden Beispiel das Vorhandensein der Dateinamenserweiterung XPS als Beleg dafür, dass es sich bei einer Datei um eine [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Datei handelt  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dateien müssen diese Erweiterung jedoch nicht haben.  Das [isXPS.exe \(isXPS\-Tool für Übereinstimmungstests\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md) ist eine Möglichkeit, eine Datei auf [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Gültigkeit zu testen.  
  
## Siehe auch  
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.AddJob%2A>   
 <xref:System.Threading.ApartmentState>   
 <xref:System.STAThreadAttribute>   
 [XPS](http://www.microsoft.com/whdc/xps/default.mspx)   
 [Printing an XPS Document](http://msdn.microsoft.com/de-de/849555c8-0c4e-48c0-86bc-a5494c69b36c)   
 [Managed and Unmanaged Threading](http://msdn.microsoft.com/de-de/db425c20-4b2f-4433-bf96-76071c7881e5)   
 [isXPS.exe \(isXPS\-Tool für Übereinstimmungstests\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)