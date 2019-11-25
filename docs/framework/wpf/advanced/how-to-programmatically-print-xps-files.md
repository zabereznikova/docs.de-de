---
title: 'Gewusst wie: Programmgesteuertes Drucken von XPS-Dateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: cc86a7e7c6a816af37c3d063825ed62583afa78a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966998"
---
# <a name="how-to-programmatically-print-xps-files"></a>Gewusst wie: Programmgesteuertes Drucken von XPS-Dateien

Sie können eine Überladung der <xref:System.Printing.PrintQueue.AddJob%2A>-Methode verwenden, um XPS-Dateien (XML Paper Specification) zu drucken, ohne eine <xref:System.Windows.Controls.PrintDialog> zu öffnen, oder im Prinzip alle [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].

Sie können XPS-Dateien auch mit den vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A?displayProperty=nameWithType>-und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A?displayProperty=nameWithType>-Methoden drucken. Weitere Informationen finden Sie unter [Drucken eines XPS-Dokuments](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).

Eine weitere Möglichkeit zum Drucken von XPS ist die Verwendung der Methoden <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A?displayProperty=nameWithType> oder <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A?displayProperty=nameWithType>. Weitere Informationen finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).

## <a name="example"></a>Beispiel

Die wichtigsten Schritte bei der Verwendung der <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode mit drei Parametern lauten wie folgt. Das folgende Beispiel enthält Details.

1. Stellen Sie fest, ob es sich bei dem Drucker um einen XPSDrv-Drucker handelt. Weitere Informationen zu XPSDrv finden Sie unter Übersicht über das [Drucken](printing-overview.md) .

2. Wenn es sich bei dem Drucker nicht um einen XPSDrv-Drucker handelt, legen Sie das Apartment des Threads auf Singlethread fest.

3. Instanziieren Sie einen Druckerserver und ein Druckwarteschlangenobjekt.

4. Ruft die-Methode auf, gibt einen Auftrags Namen, die zu druckende Datei und ein <xref:System.Boolean> Flag an, das angibt, ob es sich bei dem Drucker um einen XPSDrv-Drucker handelt.

Im folgenden Beispiel wird gezeigt, wie alle XPS-Dateien in einem Verzeichnis gedruckt werden. Obwohl die Anwendung den Benutzer auffordert, das Verzeichnis anzugeben, erfordert die <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode mit drei Parametern keine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Sie kann in jedem Codepfad verwendet werden, in dem Sie einen XPS-Dateinamen und-Pfad haben, den Sie übergeben können.

Die drei-Parameter-<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Überladung von <xref:System.Printing.PrintQueue.AddJob%2A> muss in einem einzelnen Thread Apartment ausgeführt werden, wenn der <xref:System.Boolean>-Parameter `false`ist. Dies muss sein, wenn ein nicht-XPSDrv-Drucker verwendet wird. Der Standard Apartment Zustand für .net ist jedoch mehrere Threads. Dieser Standard muss umgekehrt werden, da im Beispiel kein XPSDrv-Drucker angenommen wird.

Es gibt zwei Möglichkeiten, die Standardeinstellung zu ändern. Eine Möglichkeit besteht darin, einfach die <xref:System.STAThreadAttribute> (d. h. "`[System.STAThreadAttribute()]`") direkt oberhalb der ersten Zeile der `Main` Methode der Anwendung (in der Regel "`static void Main(string[] args)`") hinzuzufügen. Viele Anwendungen erfordern jedoch, dass die `Main`-Methode einen Multithread-Apartment Zustand aufweist. es gibt also eine zweite Methode: setzen Sie den <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> in einem separaten Thread, dessen Apartment Zustand auf <xref:System.Threading.ApartmentState.STA> mit <xref:System.Threading.Thread.SetApartmentState%2A>festgelegt ist. Im folgenden Beispiel wird dieses zweite Verfahren verwendet.

Dementsprechend beginnt das Beispiel mit dem Instanziieren eines <xref:System.Threading.Thread> Objekts und dem übergeben einer **PrintXPS** -Methode als <xref:System.Threading.ThreadStart>-Parameter. (Die **PrintXPS** -Methode wird später im Beispiel definiert.) Als nächstes wird der Thread auf ein einzelnes Thread Apartment festgelegt. Mit dem verbleibenden Code der `Main`-Methode wird der neue Thread gestartet.

In diesem Beispiel geht es im Wesentlichen um die `static`**BatchXPSPrinter.PrintXPS**-Methode. Nach dem Erstellen eines Druck Servers und einer Warteschlange wird der Benutzer von der-Methode zur Eingabe eines Verzeichnisses aufgefordert, das XPS-Dateien enthält Nachdem Sie überprüft haben, ob das Verzeichnis vorhanden ist und \*. XPS-Dateien darin vorhanden sind, fügt die Methode jede dieser Dateien der Druck Warteschlange hinzu. Im Beispiel wird davon ausgegangen, dass es sich bei dem Drucker nicht um einen XPSDrv-Drucker handelt. daher übergeben wir `false` an den letzten Parameter <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Methode. Aus diesem Grund überprüft die-Methode das XPS-Markup in der Datei, bevor versucht wird, Sie in die Seitenbeschreibungssprache des Druckers zu konvertieren. Wenn die Validierung fehlschlägt, wird eine Ausnahme ausgelöst. Der Beispielcode fängt die Ausnahme ab, benachrichtigt den Benutzer darüber und fährt dann mit der Verarbeitung der nächsten XPS-Datei fort.

[!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
[!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]

Wenn Sie einen XPSDrv-Drucker verwenden, können Sie den abschließenden Parameter auf `true` festlegen. Da XPS die Seitenbeschreibungssprache des Druckers ist, sendet die Methode die Datei an den Drucker, ohne Sie zu validieren oder in eine andere Seitenbeschreibungssprache zu wandeln. Wenn Sie zur Entwurfszeit unsicher sind, ob die Anwendung einen XPSDrv-Drucker verwendet, können Sie die Anwendung so ändern, dass Sie die <xref:System.Printing.PrintQueue.IsXpsDevice%2A>-Eigenschaft und die Verzweigung entsprechend der gefundenen Informationen liest.

Da zunächst nur wenige XPSDrv-Drucker direkt nach der Veröffentlichung von Windows Vista und Microsoft .NET Framework verfügbar sein werden, müssen Sie möglicherweise einen nicht-XPSDrv-Drucker als XPSDrv-Drucker verbergen. Fügen Sie hierzu auf dem Computer, der die Anwendung ausführt, im folgenden Registrierungsschlüssel die Datei „Pipelineconfig.xml“ zur Liste der Dateien hinzu:

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles

wobei *\<PseudoXPSPrinter>* für eine beliebige Druckwarteschlange steht. Der Computer muss anschließend neu gestartet werden.

Diese Verschleierung ermöglicht es Ihnen, `true` als letzten Parameter <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> zu übergeben, ohne dass eine Ausnahme ausgelöst wird. da *\<PseudoXPSPrinter >* jedoch nicht wirklich ein XPSDrv-Drucker ist, wird nur der Garbage Print gedruckt.

> [!NOTE]
> Der Einfachheit halber verwendet das obige Beispiel das vorhanden sein einer \*. XPS-Erweiterung als Test, dass es sich bei einer Datei um XPS handelt. XPS-Dateien müssen diese Erweiterung jedoch nicht haben. Das isXPS [. exe (isXPS-Konformitäts Tool)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) ist eine Möglichkeit, eine Datei für die XPS-Gültigkeit zu testen.

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
