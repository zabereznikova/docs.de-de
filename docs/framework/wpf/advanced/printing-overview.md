---
title: Übersicht über das Drucken
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: 4f8fd92105bd5ae09e0c1daa2e0db48b74cde77c
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68672040"
---
# <a name="printing-overview"></a>Übersicht über das Drucken
Mit Microsoft .NET Framework verfügen Anwendungsentwickler, die Windows Presentation Foundation (WPF) verwenden, über einen umfangreichen neuen Satz von Druck-und drucksystemverwaltungs-APIs. Mit [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] stehen einige dieser Erweiterungen des Drucksystems auch Entwicklern zur Verfügung, die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Anwendungen erstellen, sowie Entwicklern, die nicht verwalteten Code verwenden. Im Zentrum dieser neuen Funktionen stehen das neue [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]-Dateiformat und der [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Druckpfad.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Info über XPS  
 XPS ist ein elektronisches Dokumentformat, ein spooldateiformat und eine Seitenbeschreibungssprache. Es handelt sich um ein offenes Dokumentformat, das [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] und andere Branchenstandards verwendet, um plattformübergreifend nutzbare Dokumente zu erstellen. XPS vereinfacht den Prozess, mit dem digitale Dokumente erstellt, freigegeben, gedruckt, angezeigt und archiviert werden. Weitere Informationen zu XPS finden Sie unter [XPS-Dokumente](/windows/desktop/printdocs/documents).  
  
 Verschiedene Techniken für das Drucken von XPS-basierten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Inhalten mithilfe von sind in Programm gesteuertes [Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md)dargestellt. Es kann sinnvoll sein, diese Beispiele beim Durcharbeiten der in diesem Thema enthaltenen Inhalte hinzuzuziehen. (Entwicklern von nicht verwaltetem Code sollte die Dokumentation für die [MXDC_ESCAPE-Funktion](/windows/desktop/printdocs/mxdc-escape)angezeigt werden. Windows Forms Entwickler müssen die API im <xref:System.Drawing.Printing> -Namespace verwenden, der nicht den vollständigen [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] -Druckpfad unterstützt, aber einen Hybriden GDI-zu-XPS-Druckpfad unterstützt. Weitere Informationen finden Sie unter **Druckpfadarchitektur** unten.)  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>XPS-Druckpfad  
 Der XML Paper Specification (XPS)-Druckpfad ist ein [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] neues Feature, mit dem die Behandlung von Druck Vorgängen in Windows-Anwendungen neu definiert wird. Da [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] eine Sprache für die Dokument Darstellung (z. b. RTF), ein druckerspoolerformat (z. b. WMF) und eine Seitenbeschreibungssprache (z. b. PCL oder PostScript) ersetzen kann, behält der neue Druckpfad das XPS-Format von der Anwendungs Veröffentlichung bis zum abschließende Verarbeitung im Druckertreiber oder-Gerät.  
  
 Der XPS-Druckpfad basiert auf dem XPS-Druckertreiber Modell (XPSDrv), das Entwicklern verschiedene Vorteile bietet, wie [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] z. b. Drucken, verbesserte Farbunterstützung und erheblich verbesserte Druckleistung. (Weitere Informationen zu XPSDrv finden Sie in der [Dokumentation zum Windows-Treiberkit](/windows-hardware/drivers/).)  
  
 Der Vorgang des Druck Spoolers für XPS-Dokumente entspricht im Wesentlichen dem in früheren Versionen von Windows. Es wurde jedoch verbessert, um den XPS-Druck Pfad zusätzlich zum vorhandenen GDI-Druckpfad zu unterstützen. Der neue Druckpfad nutzt nativ eine XPS-Spooldatei. Wenngleich die für frühere Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] geschriebenen Druckertreiber für den Benutzermodus weiterhin funktionieren, ist ein XPS-Druckertreiber (XPSDrv) erforderlich, um den XPS-Druckpfad zu verwenden.  
  
 Die Vorteile des XPS-Druck Pfads sind erheblich und umfassen Folgendes:  
  
- [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)]-Druckunterstützung  
  
- Systemeigene Unterstützung für erweiterte Farbprofile, die auch 32 Bit pro Kanal (bpc), CMYK, benannte Farben, n-Tinten und systemeigene Unterstützung von Transparenz und Farbverläufen einschließen.  
  
- Verbesserte Druckleistung für .NET Framework und [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] die basierten Anwendungen.  
  
- Industriestandard-XPS-Format.  
  
 Für einfache Druck Szenarien ist eine einfache und intuitive API mit einem einzelnen Einstiegspunkt für die Benutzeroberfläche, die Konfiguration und die Auftrags Übermittlung verfügbar. Für erweiterte Szenarien steht jetzt zusätzlich Unterstützung für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Anpassung (oder Verzicht auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), synchronen oder asynchronen Druck und Funktionen zum Druck von Batchaufträgen zur Verfügung. Beide Optionen bieten Druckunterstützung mit vollständigen oder eingeschränkten Vertrauensstellungen.  
  
 XPS wurde mit Erweiterbarkeit konzipiert. Mithilfe des Erweiterbarkeits Frameworks können Features und Funktionen in einer modularen Weise zu XPS hinzugefügt werden. Zu den Erweiterungsfunktionen gehören:  
  
- Druckschema. Das öffentliche Schema wird regelmäßig aktualisiert und ermöglicht die schnelle Erweiterung von Gerätefunktionen. (Siehe dazu **PrintTicket und PrintCapabilities** unten.)  
  
- Erweiterbare Filterpipeline. Die Filter Pipeline des XPS-Druckertreibers (XPSDrv) wurde entwickelt, um das direkte und skalierbare Drucken von XPS-Dokumenten zu ermöglichen. Weitere Informationen finden Sie unter [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Druckpfadarchitektur  
 Zwar unter [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] stützen sowohl-als auch .NET Framework- [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendungen XPS, und Windows Forms Anwendungen verwenden eine GDI-zu-XPS-Konvertierung, um XPS-formatierten Inhalt für den XPS-Druckertreiber (XPSDrv) zu erstellen. Diese Anwendungen sind nicht erforderlich, um den XPS-Druckpfad zu verwenden, und können den erweiterten Metafile (EMF)-basierten Druck weiterhin verwenden. Die meisten XPS-Features und-Erweiterungen sind jedoch nur für Anwendungen verfügbar, die auf den XPS-Druckpfad abzielen.  
  
 Um die Verwendung von XPSDrv-basierten Druckern durch [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Anwendungen zu ermöglichen, unterstützt der XPS-Druckertreiber (XPSDrv) die Konvertierung von GDI in das XPS-Format. Das XPSDrv-Modell bietet auch einen Konverter für das XPS-zu-GDI-Format [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] , [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] damit Anwendungen Dokumente drucken können. Bei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendungen erfolgt die Konvertierung von XPS in das GDI-Format automatisch <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> durch <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> die-Methode <xref:System.Windows.Xps.XpsDocumentWriter> und die-Methode der-Klasse, wenn die Ziel Druck Warteschlange des Schreibvorgangs keinen XPSDrv-Treiber enthält. (Windows Forms Anwendungen können keine [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Dokumente drucken.)  
  
 In der folgenden Abbildung [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]ist das Druck Subsystem dargestellt und die von bereitgestellten Teile sowie die von Software-und Hardwareanbietern definierten Teile definiert:  
  
 ![Screenshot zeigt das XPS-Drucksystem.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Einfacher XPS-Druck  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]definiert sowohl eine einfache als auch eine erweiterte API. Für Anwendungen, für die keine umfangreiche Druckanpassung oder der vollständige Zugriff auf die vollständige XPS-Funktion erforderlich ist, ist die grundlegende Druckunterstützung verfügbar. Die einfache Druckunterstützung wird über ein Druckdialogfeld-Steuerelement verfügbar gemacht, das nur minimale Konfiguration erfordert und eine vertraute [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bietet. Viele XPS-Features sind mit diesem vereinfachten Druck Modell verfügbar.  
  
#### <a name="printdialog"></a>PrintDialog  
 Das <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> -Steuerelement stellt einen einzelnen Einstiegs [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Punkt für die-,-Konfigurations-und XPS-Auftrags Übermittlung bereit. Informationen zum Instanziieren und Verwenden des Steuerelements finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Erweiterter XPS-Druck  
 Für den Zugriff auf den vollständigen Satz von XPS-Funktionen muss die erweiterte Druck-API verwendet werden. Einige relevante APIs werden im folgenden ausführlicher beschrieben. Eine vollständige Liste der XPS-Druckpfad-APIs finden <xref:System.Windows.Xps> Sie <xref:System.Printing> unter den-und-Namespace verweisen.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket und PrintCapabilities  
 Die <xref:System.Printing.PrintTicket> - <xref:System.Printing.PrintCapabilities> Klasse und die-Klasse sind die Grundlage der erweiterten XPS-Funktionen. Beide Objekttypen sind Strukturen druckorientierter Funktionen, wie etwa Sortierung, doppelseitiger Druck, Heftung usw. im [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Format. Diese Strukturen sind durch das Druckschema definiert. Ein <xref:System.Printing.PrintTicket> weist einen Drucker an, wie ein Druckauftrag verarbeitet werden muss. Die <xref:System.Printing.PrintCapabilities> -Klasse definiert die Fähigkeiten eines Druckers. Durch Abfragen der Funktionen eines Druckers kann ein <xref:System.Printing.PrintTicket> erstellt werden, das die von einem Drucker unterstützten Funktionen in vollem Umfang nutzt. Analog dazu können nicht unterstützte Funktionen vermieden werden.  
  
 Im folgenden Beispiel wird das Abfragen der <xref:System.Printing.PrintCapabilities> eines Druckers und das Erstellen eines <xref:System.Printing.PrintTicket> mithilfe von Code gezeigt.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer und PrintQueue  
 Die <xref:System.Printing.PrintServer>-Klasse stellt einen Netzwerkdruckerserver und die <xref:System.Printing.PrintQueue>-Klasse einen Drucker mit zugeordneter Auftragswarteschlange dar. Diese APIs ermöglichen die Erweiterte Verwaltung der Druckaufträge eines Servers. Ein <xref:System.Printing.PrintServer> oder eine davon abgeleitete Klasse wird verwendet, um eine <xref:System.Printing.PrintQueue> zu verwalten. Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methode wird verwendet, um einen neuen Druckauftrag in die Warteschlange einzustellen.  
  
 Das folgende Beispiel zeigt, wie ein <xref:System.Printing.LocalPrintServer> erstellt und mithilfe von Code auf seine Standard-<xref:System.Printing.PrintQueue> zugegriffen wird.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Ein <xref:System.Windows.Xps.XpsDocumentWriter>mit den <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> vielen-und- <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden, mit denen XPS-Dokumente in ein <xref:System.Printing.PrintQueue>geschrieben werden. Beispielsweise wird die <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> -Methode verwendet, um ein XPS-Dokument <xref:System.Printing.PrintTicket> und synchron auszugeben. Die <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> -Methode wird verwendet, um ein XPS- <xref:System.Printing.PrintTicket> Dokument und asynchron auszugeben.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Xps.XpsDocumentWriter> mithilfe von Code erstellt wird.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methoden stellen ebenfalls Druckmöglichkeiten bereit. Weitere Informationen finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>GDI-Druckpfad  
 Während [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen den XPS-Druckpfad nativ unter [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] stützen, können auch Windows Forms Anwendungen einige XPS-Funktionen nutzen. Der XPS-Druckertreiber (XPSDrv) kann eine GDI-basierte Ausgabe in das XPS-Format konvertieren. Für erweiterte Szenarien wird die benutzerdefinierte Konvertierung von Inhalten mithilfe von [Microsoft XPS Document Converter (mxdc)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)unterstützt. Ebenso können [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen auch an den GDI-Druck Pfad ausgeben, indem Sie eine <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> der- <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> oder-Methoden <xref:System.Windows.Xps.XpsDocumentWriter> der-Klasse aufrufen und einen nicht-XPSDrv-Drucker als Ziel Drucker Warteschlange festlegen.  

Bei Anwendungen, für die keine XPS-Funktionalität oder-Unterstützung erforderlich ist, bleibt der aktuelle GDI-Druckpfad unverändert.  
  
- Zusätzliches Referenzmaterial zum GDI-Druckpfad und den verschiedenen XPS-Konvertierungsoptionen finden Sie unter [Microsoft XPS Document Converter (mxdc)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) und [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>XPSDrv-Treibermodell  
 Der XPS-Druckpfad verbessert die Effizienz des Spoolers durch die Verwendung von XPS als System eigenes druckspoolformat beim Drucken auf einen XPS-fähigen Drucker oder Treiber. Durch den vereinfachten Spoolvorgang entfällt die Notwendigkeit, eine zwischenspooldatei (z. b. eine EMF-Datendatei) zu generieren, bevor das Dokument gespoolert wird. Durch kleinere Spooldateien kann der XPS-Druckpfad den Netzwerkverkehr verringern und die Druckleistung verbessern.  
  
 EMF ist ein geschlossenes Format, das die Anwendungs Ausgabe als eine Reihe von Aufrufen an GDI für Renderingdienste darstellt. Anders als EMF stellt das XPS-Spoolformat das tatsächliche Dokument dar, ohne dass eine weitere Interpretation erforderlich ist, wenn es an einen XPS-basierten Druckertreiber (XPSDrv) ausgegeben wird. Die Treiber können direkt mit den Daten im vorliegenden Format arbeiten. Durch diese Funktion werden die Daten-und Farb Raum Konvertierungen vermieden, die bei der Verwendung von EMF-Dateien und GDI-basierten Druckertreibern erforderlich sind.  
  
 Spooldateigrößen werden normalerweise reduziert, wenn Sie XPS-Dokumente verwenden, die auf einen XPS-Druckertreiber (XPSDrv) abzielen, verglichen mit den EMF-Entsprechungen Allerdings gibt es Ausnahmen:  
  
- Eine Vektorgrafik, die sehr komplex ist, viele Ebenen aufweist oder ineffizient geschrieben wurde, kann größer als die Bitmapversion der gleichen Grafik sein.  
  
- Zum Zweck der Anzeige am Bildschirm werden in XPS-Dateien Geräteschriftarten sowie computerbasierte Schriftarten eingebettet, während in GDI-Spooldateien keine Geräteschriftarten eingebettet sind. Beide Schriftarten sind jedoch in Teilmengen gegliedert (siehe unten), und Druckertreiber können die Geräteschriftarten vor der Übertragung der Datei an den Drucker entfernen.  
  
 Die Reduzierung der Spoolgröße erfolgt mithilfe mehrerer Mechanismen:  
  
- **Unterklassen von Schriftarten**. Nur Zeichen, die innerhalb des eigentlichen Dokuments verwendet werden, werden in der XPS-Datei gespeichert.  
  
- **Erweiterte Grafikunterstützung**. Durch die systemeigene Unterstützung von Transparenz und Farbverlaufsprimitiven wird die Rasterung von Inhalten im [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dokument vermieden.  
  
- **Erkennung gemeinsamer Ressourcen**. Ressourcen, die mehrfach verwendet werden (wie etwa ein Bild, das ein Firmenlogo darstellt) werden als freigegebene Ressourcen behandelt und nur einmal geladen.  
  
- **ZIP-Komprimierung**. Alle XPS-Dokumente verwenden die ZIP-Komprimierung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Themen zu Vorgehensweisen](printing-how-to-topics.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [XPS-Dokumente](/windows/desktop/printdocs/documents)
- [Serialisierung und Speicherung von Dokumenten](document-serialization-and-storage.md)
- [Microsoft XPS Document Converter (mxdc)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
