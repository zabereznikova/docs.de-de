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
ms.openlocfilehash: 5571544284326fa7ce26382711f696734a166df5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254096"
---
# <a name="how-to-programmatically-print-xps-files"></a>Vorgehensweise: Programmgesteuertes Drucken von XPS-Dateien
Sie können eine Überladung der <xref:System.Printing.PrintQueue.AddJob%2A> -Methode verwenden, um XPS-Dateien (XML Paper Specification) zu drucken, ohne ein <xref:System.Windows.Controls.PrintDialog> -oder [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] -Prinzip (grundsätzlich) zu öffnen.  
  
 Sie können XPS-Dateien auch mit den vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A?displayProperty=nameWithType> Methoden <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A?displayProperty=nameWithType> und drucken. Weitere Informationen finden Sie unter [Drucken eines XPS-Dokuments](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).  
  
 Eine weitere Möglichkeit zum Drucken von XPS ist die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A?displayProperty=nameWithType> Verwendung <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A?displayProperty=nameWithType> der-Methode oder der-Methode. Weitere Informationen finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Beispiel  
 Die wichtigsten Schritte bei der Verwendung der Methode mit <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> drei Parametern lauten wie folgt. Das folgende Beispiel enthält Details.  
  
1. Stellen Sie fest, ob es sich bei dem Drucker um einen XPSDrv-Drucker handelt. (Weitere Informationen zu XPSDrv finden Sie unter [Übersicht über das Drucken](printing-overview.md).)  
  
2. Wenn es sich bei dem Drucker nicht um einen XPSDrv-Drucker handelt, legen Sie das Apartment des Threads auf Singlethread fest.  
  
3. Instanziieren Sie einen Druckerserver und ein Druckwarteschlangenobjekt.  
  
4. Ruft die-Methode auf, gibt einen Auftrags Namen, die zu druckende Datei und <xref:System.Boolean> ein Flag an, das angibt, ob es sich bei dem Drucker um einen XPSDrv-Drucker handelt.  
  
 Im folgenden Beispiel wird gezeigt, wie alle XPS-Dateien in einem Verzeichnis gedruckt werden. Obwohl die Anwendung den Benutzer auffordert, das Verzeichnis anzugeben, <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]erfordert die Methode mit drei Parametern keine. Sie kann in jedem Codepfad verwendet werden, in dem Sie einen XPS-Dateinamen und-Pfad haben, den Sie übergeben können.  
  
 Die drei Parameter <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Überladung von <xref:System.Printing.PrintQueue.AddJob%2A> muss in einem Single Thread-Apartment ausgeführt werden, wenn `false`der <xref:System.Boolean> -Parameter ist. Dies muss sein, wenn ein nicht-XPSDrv-Drucker verwendet wird. Der Standard Apartment Zustand für .net ist jedoch mehrere Threads. Dieser Standard muss umgekehrt werden, da im Beispiel kein XPSDrv-Drucker angenommen wird.  
  
 Es gibt zwei Möglichkeiten, die Standardeinstellung zu ändern. Eine Möglichkeit besteht darin, einfach das <xref:System.STAThreadAttribute> (`[System.STAThreadAttribute()]`d. h. "") direkt oberhalb der ersten Zeile der- `Main` Methode der Anwendung (in`static void Main(string[] args)`der Regel "") hinzuzufügen. Viele Anwendungen erfordern jedoch, dass die `Main` -Methode einen Multithread-Apartment Zustand aufweist. es gibt also eine zweite Methode: Platzieren Sie <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> den-Befehl in einem separaten Thread, dessen Apartment <xref:System.Threading.Thread.SetApartmentState%2A>Zustand <xref:System.Threading.ApartmentState.STA> auf festgelegt ist. Im folgenden Beispiel wird dieses zweite Verfahren verwendet.  
  
 Dementsprechend beginnt das Beispiel mit dem Instanziieren eines <xref:System.Threading.Thread> -Objekts und dem übergeben einer **PrintXPS** -Methode <xref:System.Threading.ThreadStart> als Parameter. (Die **PrintXPS**-Methode wird später im Beispiel definiert.) Danach wird der Thread auf ein Singlethreadapartment festgelegt. Mit dem verbleibenden Code der `Main`-Methode wird der neue Thread gestartet.  
  
 In diesem Beispiel geht es im Wesentlichen um die `static`**BatchXPSPrinter.PrintXPS**-Methode. Nach dem Erstellen eines Druck Servers und einer Warteschlange wird der Benutzer von der-Methode zur Eingabe eines Verzeichnisses aufgefordert, das XPS-Dateien enthält Nachdem Sie überprüft haben, ob das Verzeichnis vorhanden ist und ob \*XPS-Dateien darin vorhanden sind, fügt die Methode jede dieser Dateien der Druck Warteschlange hinzu. Bei dem Beispiel wird davon ausgegangen, dass es sich bei dem Drucker nicht um einen XPSDrv-Drucker handelt <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> , daher wird der letzte Parameter der-Methode übergeben `false` . Aus diesem Grund überprüft die-Methode das XPS-Markup in der Datei, bevor versucht wird, Sie in die Seitenbeschreibungssprache des Druckers zu konvertieren. Wenn die Validierung fehlschlägt, wird eine Ausnahme ausgelöst. Der Beispielcode fängt die Ausnahme ab, benachrichtigt den Benutzer darüber und fährt dann mit der Verarbeitung der nächsten XPS-Datei fort.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Wenn Sie einen XPSDrv-Drucker verwenden, können Sie den abschließenden Parameter auf `true` festlegen. Da XPS die Seitenbeschreibungssprache des Druckers ist, sendet die Methode die Datei an den Drucker, ohne Sie zu validieren oder in eine andere Seitenbeschreibungssprache zu wandeln. Wenn Sie zur Entwurfszeit unsicher sind, ob die Anwendung einen XPSDrv-Drucker verwendet, können Sie die Anwendung so ändern, dass Sie die <xref:System.Printing.PrintQueue.IsXpsDevice%2A> Eigenschaft und Verzweigung entsprechend der gefundenen Informationen liest.  
  
 Da anfänglich nur wenige XPSDrv-Drucker direkt nach der Veröffentlichung von [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] und Microsoft .NET Framework verfügbar sein werden, müssen Sie möglicherweise einen nicht-XPSDrv-Drucker als XPSDrv-Drucker verbergen. Fügen Sie hierzu auf dem Computer, der die Anwendung ausführt, im folgenden Registrierungsschlüssel die Datei „Pipelineconfig.xml“ zur Liste der Dateien hinzu:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles  
  
 wobei *\<PseudoXPSPrinter>* für eine beliebige Druckwarteschlange steht. Der Computer muss anschließend neu gestartet werden.  
  
 Diese Verschleierung ermöglicht Ihnen, als letzten `true` Parameter von <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> zu übergeben, ohne dass eine Ausnahme ausgelöst wird. da  *\<PseudoXPSPrinter >* jedoch nicht wirklich ein XPSDrv-Drucker ist, wird nur der Garbage Print gedruckt.  
  
 **Hinweis** Der Einfachheit halber verwendet das obige Beispiel das vorhanden sein einer \*XPS-Erweiterung als Test, dass es sich bei einer Datei um XPS handelt. XPS-Dateien müssen diese Erweiterung jedoch nicht haben. Das isXPS [. exe (isXPS-Konformitäts Tool)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) ist eine Möglichkeit, eine Datei für die XPS-Gültigkeit zu testen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [XPS-Dokumente](/windows/desktop/printdocs/documents)
- [Drucken eines XPS-Dokuments](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [Verwaltetes und nicht verwaltetes Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe (isXPS-Tool für Übereinstimmungstests)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
