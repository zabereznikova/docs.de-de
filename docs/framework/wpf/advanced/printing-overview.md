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
ms.openlocfilehash: f82fd9803512dbd2466c4d0b49142e2c553d578a
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380230"
---
# <a name="printing-overview"></a>Übersicht über das Drucken
Anwendungsentwickler, die mit Windows Presentation Foundation (WPF) haben ein neues umfassendes Set an drucken und drucksystemverwaltung APIs, mit Microsoft .NET Framework. Mit [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] stehen einige dieser Erweiterungen des Drucksystems auch Entwicklern zur Verfügung, die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Anwendungen erstellen, sowie Entwicklern, die nicht verwalteten Code verwenden. Im Zentrum dieser neuen Funktionen stehen das neue [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]-Dateiformat und der [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Druckpfad.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Info über XPS  
 XPS ist ein Format für elektronische Dokumente, ein Format für Spooldateien und eine Seitenbeschreibungssprache. Es handelt sich um ein offenes Dokumentformat, das [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] und andere Branchenstandards verwendet, um plattformübergreifend nutzbare Dokumente zu erstellen. XPS vereinfacht den Prozess mit dem digitale Dokumente erstellt, freigegebene, gedruckt, angezeigt und archiviert werden. Weitere Informationen zum XPS, finden Sie unter [XPS-Dokumente](/windows/desktop/printdocs/documents).  
  
 Verschiedene Techniken zum Drucken XPS-basierten Inhalt mithilfe [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] werden veranschaulicht [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md). Es kann sinnvoll sein, diese Beispiele beim Durcharbeiten der in diesem Thema enthaltenen Inhalte hinzuzuziehen. (Entwickler von nicht verwaltetem Code sollten finden Sie in der Dokumentation für die [MXDC_ESCAPE Funktion](/windows/desktop/printdocs/mxdc-escape). Windows Forms-Entwickler verwenden, müssen die [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] in die <xref:System.Drawing.Printing> Namespace, der die vollständige nicht unterstützt. [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Druckpfad, wohl aber einen Hybriden GDI-nach-XPS-Druckpfad unterstützt. Weitere Informationen finden Sie unter **Druckpfadarchitektur** unten.)  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>XPS-Druckpfad  
 Die XML Paper Specification (XPS)--Druckpfad ist ein neues [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] -Funktion, die definiert, wie Drucken in Windows-Anwendungen ausgeführt wird. Da [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] können eine Sprache (wie etwa RTF), ein druckerspoolerformat (wie etwa WMF) und eine Seitenbeschreibungssprache (wie z. B. PCL oder Postscript) ersetzen, die im neuen Druckpfad des XPS-Format aus der Veröffentlichung der Anwendung, die die letzte Verarbeitung im Druckertreiber oder-Gerät.  
  
 Das XPS-Druckpfad baut auf das XPS-druckertreibermodell (XPSDrv), bietet mehrere Vorteile für Entwickler, wie z. B. [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] Druck, verbesserte farbunterstützung und erheblich gesteigerte druckleistung. (Weitere Informationen zu XPSDrv finden Sie unter den [Windows Driver Kit Dokumentation](/windows-hardware/drivers/).)  
  
 Der Vorgang des druckerspoolers ist für XPS-Dokumente ist im Grunde das gleiche wie in früheren Versionen von Windows. Aber es wurde verbessert, um zusätzlich zu den bestehenden der XPS-Druckpfad unterstützt [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] -Druckpfad. Der neue Druckpfad nutzt systemeigen Spool XPS-Datei. Während im Benutzermodus Druckertreiber für frühere Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funktionieren weiterhin, das ein XPS-Druckertreiber (XPSDrv) ist erforderlich, um das XPS-Druckpfad verwenden.  
  
 Die Vorteile der XPS-Druckpfad sind erheblich und umfassen:  
  
- [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)]-Druckunterstützung  
  
- Systemeigene Unterstützung für erweiterte Farbprofile, die auch 32 Bit pro Kanal (bpc), CMYK, benannte Farben, n-Tinten und systemeigene Unterstützung von Transparenz und Farbverläufen einschließen.  
  
- Verbesserte druckleistung für .NET Framework und [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] -basierte Anwendungen.  
  
- Format nach Industriestandard XPS.  
  
 Für einfache Druckszenarien ist eine einfache und intuitiv bedienbare [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] mit einem einzelnen Einstiegspunkt für Benutzeroberfläche, Konfiguration und Auftragsübergabe verfügbar. Für erweiterte Szenarien steht jetzt zusätzlich Unterstützung für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Anpassung (oder Verzicht auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), synchronen oder asynchronen Druck und Funktionen zum Druck von Batchaufträgen zur Verfügung. Beide Optionen bieten Druckunterstützung mit vollständigen oder eingeschränkten Vertrauensstellungen.  
  
 XPS wurde unter berücksichtung der Erweiterbarkeit entwickelt. Mit dem Extensibility Framework, können Features und Funktionen auf modulare Weise in XPS hinzugefügt werden. Zu den Erweiterungsfunktionen gehören:  
  
- Druckschema. Das öffentliche Schema wird regelmäßig aktualisiert und ermöglicht die schnelle Erweiterung von Gerätefunktionen. (Siehe dazu **PrintTicket und PrintCapabilities** unten.)  
  
- Erweiterbare Filterpipeline. Die Filterpipeline von XPS Drucker-Druckertreiber (XPSDrv) wurde entwickelt, um sowohl direkte als auch skalierbaren Druck von XPS-Dokumenten zu aktivieren. Weitere Informationen finden Sie unter [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Druckpfadarchitektur  
 Während beide [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und .NET Framework-Anwendungen unterstützen, XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Anwendungen verwenden eine [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] in XPS formatiert Konvertierung um XPS erstellen Inhalt für den XPS-Druckertreiber (XPSDrv). Diese Anwendungen nicht mit dem XPS-Druckpfad erforderlich sind, und können weiterhin [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)] -basierten Druck. Die meisten XPS-Features und Verbesserungen sind jedoch nur für Anwendungen, die das XPS-Druckpfad verfügbar.  
  
 So aktivieren Sie die Verwendung von XPSDrv-basierten Druckern durch [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Anwendungen, die der XPS-Druckertreiber (XPSDrv) unterstützt die Konvertierung von [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] in XPS formatiert. Das XPSDrv-Modell umfasst außerdem einen Konverter für XPS, [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] Format, damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] können Anwendungen Drucken [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Dokumente. Für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen erfolgt die Konvertierung von XPS, [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] Format erfolgt automatisch durch die <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter> Klasse, wenn die Druckerwarteschlange des Schreibvorgangs nicht über einen XPSDrv-Treiber verfügt. (Windows Forms-Anwendungen nicht drucken [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Dokumente.)  
  
 Die folgende Abbildung zeigt das Drucken-Subsystem und definiert die Teile von bereitgestellten [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)], und die von Software- und Hardwareherstellern definierten Anteile:  
  
 ![Screenshot zeigt, dass das System die XPS-Druckpfad.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Einfacher XPS-Druck  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definiert sowohl eine einfache als auch eine erweiterte [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]. Für diese Anwendungen, die keine umfangreichen drucken oder Zugriff auf die vollständige XPS-Funktion erfordern ist festgelegt ist, einfache druckunterstützung verfügbar. Die einfache Druckunterstützung wird über ein Druckdialogfeld-Steuerelement verfügbar gemacht, das nur minimale Konfiguration erfordert und eine vertraute [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bietet. Viele XPS-Funktionen sind mit diesem vereinfachten Druckmodell verfügbar.  
  
#### <a name="printdialog"></a>PrintDialog  
 Die <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Steuerelement bietet einen einzigen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und XPS-Auftragsübermittlung. Informationen zum Instanziieren und Verwenden des Steuerelements finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Erweiterter XPS-Druck  
 Den vollständigen Satz von XPS-Zugriff auf Funktionen, die erweiterte Drucken [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] muss verwendet werden. Mehrere relevante [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] sind ausführlicher unten beschrieben. Eine vollständige Liste von XPS-Druckpfad [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], finden Sie unter den <xref:System.Windows.Xps> und <xref:System.Printing> Namespaceverweise.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket und PrintCapabilities  
 Die <xref:System.Printing.PrintTicket> und <xref:System.Printing.PrintCapabilities> Klassen sind die Grundlage für die erweiterten Funktionen von XPS. Beide Objekttypen sind Strukturen druckorientierter Funktionen, wie etwa Sortierung, doppelseitiger Druck, Heftung usw. im [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Format. Diese Strukturen sind durch das Druckschema definiert. Ein <xref:System.Printing.PrintTicket> weist einen Drucker an, wie ein Druckauftrag verarbeitet werden muss. Die <xref:System.Printing.PrintCapabilities> -Klasse definiert die Fähigkeiten eines Druckers. Durch Abfragen der Funktionen eines Druckers kann ein <xref:System.Printing.PrintTicket> erstellt werden, das die von einem Drucker unterstützten Funktionen in vollem Umfang nutzt. Analog dazu können nicht unterstützte Funktionen vermieden werden.  
  
 Im folgenden Beispiel wird das Abfragen der <xref:System.Printing.PrintCapabilities> eines Druckers und das Erstellen eines <xref:System.Printing.PrintTicket> mithilfe von Code gezeigt.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer und PrintQueue  
 Die <xref:System.Printing.PrintServer>-Klasse stellt einen Netzwerkdruckerserver und die <xref:System.Printing.PrintQueue>-Klasse einen Drucker mit zugeordneter Auftragswarteschlange dar. In Kombination ermöglichen diese [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] die erweiterte Verwaltung der Druckaufträge von Servern. Ein <xref:System.Printing.PrintServer> oder eine davon abgeleitete Klasse wird verwendet, um eine <xref:System.Printing.PrintQueue> zu verwalten. Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methode wird verwendet, um einen neuen Druckauftrag in die Warteschlange einzustellen.  
  
 Das folgende Beispiel zeigt, wie ein <xref:System.Printing.LocalPrintServer> erstellt und mithilfe von Code auf seine Standard-<xref:System.Printing.PrintQueue> zugegriffen wird.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Ein <xref:System.Windows.Xps.XpsDocumentWriter>, mit seinen vielen der <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden wird zum Schreiben von XPS-Dokumente zu einer <xref:System.Printing.PrintQueue>. Z. B. die <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> Methode wird verwendet, um die Ausgabe eines XPS-Dokuments und <xref:System.Printing.PrintTicket> synchron. Die <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> Methode wird verwendet, um die Ausgabe eines XPS-Dokuments und <xref:System.Printing.PrintTicket> asynchron.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Xps.XpsDocumentWriter> mithilfe von Code erstellt wird.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methoden stellen ebenfalls Druckmöglichkeiten bereit. Weitere Informationen finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>GDI-Druckpfad  
 Während [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen nativ unterstützen das XPS-Druckpfad [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Anwendungen können auch einige XPS-Funktionen profitieren. Das XPS--Druckertreiber (XPSDrv) konvertieren kann [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] -basierte Ausgaben in XPS-Format. Für erweiterte Szenarien wird eine benutzerdefinierte Konvertierung des Inhalts unterstützt, mit der [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Auf ähnliche Weise [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen ebenfalls Ausgaben an den [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] Druckpfad durch Aufrufen einer der der <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> oder <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter> Druckwarteschlange für Klassen- und nicht-XpsDrv-Drucker als Ziel festlegen.  

Für Anwendungen, die nicht, XPS-Funktionen "oder" Support "," das aktuelle erforderlich ist [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] Druckpfad bleibt unverändert.  
  
- Zusätzliches Referenzmaterial für die [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] -Druckerpfad und die verschiedenen Optionen des XPS-Konvertierung, finden Sie unter [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) und [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>XPSDrv-Treibermodell  
 Das XPS-Druckpfad verbessert die Effizienz des spoolings mithilfe von XPS als systemeigenem druckerspoolerformat beim Drucken in ein XPS--fähigen Druckern oder Treibern. Das vereinfachte Spooling beseitigt die Notwendigkeit, vor dem Spoolen des Dokuments eine temporäre Spoolingdatei, wie etwa eine [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)]-Datendatei, zu generieren. Durch geringere Größe der Spooldateien kann das XPS-Druckpfad Netzwerkverkehr verringern und die druckleistung verbessern.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] ist ein geschlossenes Format, das Anwendungsausgaben als Abfolge von Aufrufen an [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] für Renderdienste darstellt. Im Gegensatz zu [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], der XPS--spoolingformat das tatsächliche Dokument dar, ohne dass weitere Interpretation, die bei der Ausgabe an ein XPS-basierter-Druckertreiber (XPSDrv). Die Treiber können direkt mit den Daten im vorliegenden Format arbeiten. Durch diese Fähigkeit entfallen die Daten- und Farbraumkonvertierungen, die bei der Verwendung von [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)]-Dateien und [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]-basierten Druckertreibern erforderlich sind.  
  
 Größe der Spooldateien normalerweise verringert sich die bei der Verwendung von XPS-Dokumente, die als ein XPS--Druckertreiber (XPSDrv Ziel) im Vergleich zu ihren [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] Entsprechungen; es gibt jedoch Ausnahmen:  
  
- Eine Vektorgrafik, die sehr komplex ist, viele Ebenen aufweist oder ineffizient geschrieben wurde, kann größer als die Bitmapversion der gleichen Grafik sein.  
  
- Zum Zweck der Anzeige am Bildschirm werden in XPS-Dateien Geräteschriftarten sowie computerbasierte Schriftarten eingebettet, während in GDI-Spooldateien keine Geräteschriftarten eingebettet sind. Beide Schriftarten sind jedoch in Teilmengen gegliedert (siehe unten), und Druckertreiber können die Geräteschriftarten vor der Übertragung der Datei an den Drucker entfernen.  
  
 Die Reduzierung der Spoolgröße erfolgt mithilfe mehrerer Mechanismen:  
  
- **Unterklassen von Schriftarten**. Nur Zeichen im Dokument verwendet werden, werden in die XPS-Datei gespeichert.  
  
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
- [Microsoft XPS-Dokument Konverter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
