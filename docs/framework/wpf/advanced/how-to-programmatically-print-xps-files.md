---
title: 'Vorgehensweise: Programmgesteuertes Drucken von XPS-Dateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: 1d6d45289c9278271a7c7bef5225ad024a5ab0fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312071"
---
# <a name="how-to-programmatically-print-xps-files"></a>Vorgehensweise: Programmgesteuertes Drucken von XPS-Dateien
Können Sie eine Überladung von der <xref:System.Printing.PrintQueue.AddJob%2A> Methode zum Drucken [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] Dateien ohne Öffnen eine <xref:System.Windows.Controls.PrintDialog> oder, im Prinzip alle [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] überhaupt.  
  
 Sie können auch drucken [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] von Dateien mit vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter>. Weitere Informationen dazu finden Sie unter [Drucken eines XPS-Dokuments](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).  
  
 Eine weitere Möglichkeit, Drucken [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] ist die Verwendung der <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> oder <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> Methoden der <xref:System.Windows.Controls.PrintDialog> Steuerelement. Weitere Informationen finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte zur Verwendung der dreiparametrigen <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode lauten wie folgt. Das folgende Beispiel enthält die Details.  
  
1. Stellen Sie fest, ob es sich bei dem Drucker um einen XPSDrv-Drucker handelt. (Weitere Informationen zu XPSDrv finden Sie unter [Übersicht über das Drucken](printing-overview.md).)  
  
2. Wenn es sich bei dem Drucker nicht um einen XPSDrv-Drucker handelt, legen Sie das Apartment des Threads auf Singlethread fest.  
  
3. Instanziieren Sie einen Druckerserver und ein Druckwarteschlangenobjekt.  
  
4. Rufen Sie die Methode, und geben einen Auftragsnamen an, die Datei gedruckt werden, und ein <xref:System.Boolean> flag zum angeben, ob der Drucker einen XPSDrv-Drucker ist.  
  
 Im folgenden Beispiel wird gezeigt, wie alle [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dateien in einem Verzeichnis als Batch gedruckt werden. Obwohl die Anwendung den Benutzer das Verzeichnis angeben, wird die dreiparametrige fordert <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode ist nicht erforderlich, eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Sie kann in jedem Codepfad verwendet werden, in dem ein [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dateiname und -Pfad vorhanden sind, die an sie übergeben werden können.  
  
 Die dreiparametrige <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Überladung der <xref:System.Printing.PrintQueue.AddJob%2A> muss in einem Singlethread-Apartment ausgeführt immer die <xref:System.Boolean> Parameter `false`, dies ist gegeben, wenn kein XPSDrv Drucker verwendet wird. Mehrere Threads sind jedoch der Standardapartmentzustand für [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]. Dieser Standard muss umgekehrt werden, da im Beispiel kein XPSDrv-Drucker angenommen wird.  
  
 Es gibt zwei Möglichkeiten, die Standardeinstellung zu ändern. Eine Möglichkeit besteht darin, fügen Sie einfach die <xref:System.STAThreadAttribute> (d. h. "`[System.STAThreadAttribute()]`") direkt über die erste Zeile der Anwendung `Main` Methode (in der Regel "`static void Main(string[] args)`"). Viele Anwendungen erfordern jedoch, die die `Main` -Methode verfügen über einen Multithread-Apartment-Zustand, es gibt also eine zweite Methode: Legen Sie den Aufruf zum <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> in einem separaten Thread, dessen Apartmentzustand NA hodnotu nastaven <xref:System.Threading.ApartmentState.STA> mit <xref:System.Threading.Thread.SetApartmentState%2A>. Im folgenden Beispiel wird dieses zweite Verfahren verwendet.  
  
 Das Beispiel beginnt entsprechend durch Instanziieren einer <xref:System.Threading.Thread> Objekt und die Übergabe einer **PrintXPS** -Methode, wie der <xref:System.Threading.ThreadStart> Parameter. (Die **PrintXPS**-Methode wird später im Beispiel definiert.) Danach wird der Thread auf ein Singlethreadapartment festgelegt. Mit dem verbleibenden Code der `Main`-Methode wird der neue Thread gestartet.  
  
 In diesem Beispiel geht es im Wesentlichen um die `static`**BatchXPSPrinter.PrintXPS**-Methode. Nach dem Erstellen eines Druckerservers und einer Druckwarteschlange wird der Benutzer von der Methode aufgefordert, ein Verzeichnis anzugeben, das [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dateien enthält. Nach der Überprüfung, ob das Verzeichnis vorhanden ist und das Vorhandensein der \*XPS-Dateien darin, die Methode fügt jede dieser Dateien der Druckwarteschlange hinzu. Im Beispiel wird davon ausgegangen, dass der Drucker nicht-XPSDrv, ist, sodass übergeben wird `false` der vorletzte Parameter von <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode. Aus diesem Grund überprüft die Methode das [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Markup in der Datei, bevor sie versucht, es in die Seitenbeschreibungssprache des Druckers umzuwandeln. Wenn die Validierung fehlschlägt, wird eine Ausnahme ausgelöst. Im Beispielcode wird die Ausnahme abgefangen, der Benutzer wird darüber informiert, und anschließend wird die nächste [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Datei verarbeitet.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Wenn Sie einen XPSDrv-Drucker verwenden, können Sie den abschließenden Parameter auf `true` festlegen. Da [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] die Seitenbeschreibungssprache des Druckers ist, sendet die Methode in diesem Fall die Datei ohne Überprüfung oder Umwandlung in eine andere Seitenbeschreibungssprache an den Drucker. Wenn Sie sich zur Entwurfszeit sind, ob die Anwendung einen XPSDrv-Drucker verwendet werden, können Sie die Anwendung haben sie ändern die <xref:System.Printing.PrintQueue.IsXpsDevice%2A> -Eigenschaft und die Verzweigung was es findet.  
  
 Da es anfangs nur wenige XPSDrv-Drucker sofort nach der Veröffentlichung von stehen [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] und Microsoft .NET Framework, müssen Sie möglicherweise einen nicht-XPSDrv-Drucker als XPSDrv-Drucker tarnen. Fügen Sie hierzu auf dem Computer, der die Anwendung ausführt, im folgenden Registrierungsschlüssel die Datei „Pipelineconfig.xml“ zur Liste der Dateien hinzu:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\*\<PseudoXPSPrinter>* \DependentFiles  
  
 wobei *\<PseudoXPSPrinter>* für eine beliebige Druckwarteschlange steht. Der Computer muss anschließend neu gestartet werden.  
  
 Können Sie übergeben `true` als letzten Parameter des <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> ohne eine Ausnahme verursacht, da  *\<PseudoXPSPrinter >* ist nicht wirklich ein XPSDrv-Drucker auslösen.  
  
 **Beachten Sie** der Einfachheit halber das obige Beispiel verwendet das Vorhandensein einer \*.xps Erweiterung als Beleg dafür, die eine Datei ist [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dateien müssen diese Erweiterung jedoch nicht haben. [isXPS.exe (isXPS-Tool für Übereinstimmungstests)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) ist eine Möglichkeit, eine Datei auf [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Gültigkeit zu testen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [XPS-Dokumente](/windows/desktop/printdocs/documents)
- [Drucken eines XPS-Dokuments](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [Verwaltete und nicht verwaltetes Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe (isXPS-Tool für Übereinstimmungstests)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
