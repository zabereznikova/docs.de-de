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
ms.openlocfilehash: 3f99b0e93e6b16ac66f6869c284c1119ddfc3751
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740305"
---
# <a name="printing-overview"></a>Übersicht über das Drucken
Mit Microsoft .NET Framework verfügen Anwendungsentwickler, die Windows Presentation Foundation (WPF) verwenden, über einen umfangreichen neuen Satz von Druck-und drucksystemverwaltungs-APIs. Mit Windows Vista sind einige dieser Erweiterungen des Drucksystems auch für Entwickler verfügbar, die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendungen und Entwicklern mit nicht verwaltetem Code erstellen. Der Kern dieser neuen Funktionalität ist das neue XPS-Dateiformat (XML Paper Specification) und der XPS-Druckpfad.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Info über XPS  
 XPS ist ein elektronisches Dokumentformat, ein spooldateiformat und eine Seitenbeschreibungssprache. Es handelt sich um ein offenes Dokumentformat, in dem XML, Open Packaging Conventions (OPC) und andere Industriestandards zum Erstellen von plattformübergreifenden Dokumenten verwendet werden. XPS vereinfacht den Prozess, mit dem digitale Dokumente erstellt, freigegeben, gedruckt, angezeigt und archiviert werden. Weitere Informationen zu XPS finden Sie unter [XPS-Dokumente](/windows/desktop/printdocs/documents).  
  
 Verschiedene Verfahren zum Drucken von XPS-basiertem Inhalt mithilfe von WPF werden Unterprogramm gesteuertes [Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md)veranschaulicht. Es kann sinnvoll sein, diese Beispiele beim Durcharbeiten der in diesem Thema enthaltenen Inhalte hinzuzuziehen. (Entwickler von nicht verwaltetem Code sollten die Dokumentation für die [MXDC_ESCAPE-Funktion](/windows/desktop/printdocs/mxdc-escape)sehen. Windows Forms Entwickler müssen die API im <xref:System.Drawing.Printing>-Namespace verwenden, der nicht den vollständigen XPS-Druckpfad unterstützt, aber einen Hybriden GDI-zu-XPS-Druckpfad unterstützt. Weitere Informationen finden Sie unter **Druckpfadarchitektur** unten.)  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>XPS-Druckpfad  
 Der XML Paper Specification (XPS)-Druckpfad ist ein neues Windows-Feature, mit dem die Behandlung von Druck Vorgängen in Windows-Anwendungen neu definiert wird. Da XPS eine Dokument Präsentations Sprache (z. b. RTF), ein druckerspoolerformat (z. b. WMF) und eine Seitenbeschreibungssprache (z. b. PCL oder PostScript) ersetzen kann, der neue Druckpfad behält das XPS-Format von der Anwendungs Veröffentlichung bis zur abschließenden Verarbeitung im Druckertreiber oder-Gerät bei.  
  
 Der XPS-Druckpfad basiert auf dem XPS-Druckertreiber Modell (XPSDrv), das Entwicklern einige Vorteile bietet, wie z. b. "was Sie sehen, was Sie erhalten" (WYSIWYG) Druck, verbesserte Farbunterstützung und erheblich verbesserte Druckleistung. (Weitere Informationen zu XPSDrv finden Sie in der [Dokumentation zum Windows-Treiberkit](/windows-hardware/drivers/).)  
  
 Der Vorgang des Druck Spoolers für XPS-Dokumente entspricht im Wesentlichen dem in früheren Versionen von Windows. Es wurde jedoch verbessert, um den XPS-Druck Pfad zusätzlich zum vorhandenen GDI-Druckpfad zu unterstützen. Der neue Druckpfad nutzt nativ eine XPS-Spooldatei. Obwohl für frühere Versionen von Windows geschriebene Druckertreiber für den Benutzermodus weiterhin funktionieren, ist ein XPS-Druckertreiber (XPSDrv) erforderlich, um den XPS-Druckpfad zu verwenden.  
  
 Die Vorteile des XPS-Druck Pfads sind erheblich und umfassen Folgendes:  
  
- WYSIWYG-Druckunterstützung  
  
- Systemeigene Unterstützung für erweiterte Farbprofile, die auch 32 Bit pro Kanal (bpc), CMYK, benannte Farben, n-Tinten und systemeigene Unterstützung von Transparenz und Farbverläufen einschließen.  
  
- Verbesserte Druckleistung für .NET Framework-und Win32-basierte Anwendungen.  
  
- Industriestandard-XPS-Format.  
  
 Für einfache Druck Szenarien ist eine einfache und intuitive API mit einem einzelnen Einstiegspunkt für die Benutzeroberfläche, die Konfiguration und die Auftrags Übermittlung verfügbar. Für erweiterte Szenarien steht jetzt zusätzlich Unterstützung für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Anpassung (oder Verzicht auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), synchronen oder asynchronen Druck und Funktionen zum Druck von Batchaufträgen zur Verfügung. Beide Optionen bieten Druckunterstützung mit vollständigen oder eingeschränkten Vertrauensstellungen.  
  
 XPS wurde mit Erweiterbarkeit konzipiert. Mithilfe des Erweiterbarkeits Frameworks können Features und Funktionen in einer modularen Weise zu XPS hinzugefügt werden. Zu den Erweiterungsfunktionen gehören:  
  
- Druckschema. Das öffentliche Schema wird regelmäßig aktualisiert und ermöglicht die schnelle Erweiterung von Gerätefunktionen. (Siehe dazu **PrintTicket und PrintCapabilities** unten.)  
  
- Erweiterbare Filterpipeline. Die Filter Pipeline des XPS-Druckertreibers (XPSDrv) wurde entwickelt, um das direkte und skalierbare Drucken von XPS-Dokumenten zu ermöglichen. Weitere Informationen finden Sie unter [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Druckpfadarchitektur  
 Obwohl sowohl Win32-als auch .NET Framework-Anwendungen XPS unterstützen, verwenden Win32-und Windows Forms-Anwendungen eine GDI-zu-XPS-Konvertierung, um XPS-formatierten Inhalt für den XPS-Druckertreiber (XPSDrv) zu erstellen. Diese Anwendungen sind nicht erforderlich, um den XPS-Druckpfad zu verwenden, und können den erweiterten Metafile (EMF)-basierten Druck weiterhin verwenden. Die meisten XPS-Features und-Erweiterungen sind jedoch nur für Anwendungen verfügbar, die auf den XPS-Druckpfad abzielen.  
  
 Um die Verwendung von XPSDrv-basierten Druckern durch Win32-und Windows Forms-Anwendungen zu ermöglichen, unterstützt der XPS-Druckertreiber (XPSDrv) die Konvertierung von GDI in das XPS-Format. Das XPSDrv-Modell stellt außerdem einen Konverter für das XPS-zu-GDI-Format bereit, sodass Win32-Anwendungen XPS-Dokumente drucken können. Bei WPF-Anwendungen erfolgt die Konvertierung von XPS in das GDI-Format automatisch durch die Methoden <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> der <xref:System.Windows.Xps.XpsDocumentWriter>-Klasse, wenn die Ziel Druck Warteschlange des Schreibvorgangs keinen XPSDrv-Treiber enthält. (Windows Forms Anwendungen können keine XPS-Dokumente drucken.)  
  
 In der folgenden Abbildung ist das Druck Subsystem dargestellt und die von Microsoft bereitgestellten Teile sowie die von Software-und Hardwareanbietern definierten Teile definiert:  
  
 ![Screenshot zeigt das XPS-Drucksystem.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Einfacher XPS-Druck  
 WPF definiert sowohl eine einfache als auch eine erweiterte API. Für Anwendungen, für die keine umfangreiche Druckanpassung oder der vollständige Zugriff auf die vollständige XPS-Funktion erforderlich ist, ist die grundlegende Druckunterstützung verfügbar. Die einfache Druckunterstützung wird über ein Druckdialogfeld-Steuerelement verfügbar gemacht, das nur minimale Konfiguration erfordert und eine vertraute [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bietet. Viele XPS-Features sind mit diesem vereinfachten Druck Modell verfügbar.  
  
#### <a name="printdialog"></a>PrintDialog  
 Das <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>-Steuerelement stellt einen einzelnen Einstiegspunkt für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-, Konfigurations-und XPS-Auftrags Übermittlung bereit. Informationen zum Instanziieren und Verwenden des Steuerelements finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Erweiterter XPS-Druck  
 Für den Zugriff auf den vollständigen Satz von XPS-Funktionen muss die erweiterte Druck-API verwendet werden. Einige relevante APIs werden im folgenden ausführlicher beschrieben. Eine vollständige Liste der XPS-Druckpfad-APIs finden Sie in den <xref:System.Windows.Xps>-und <xref:System.Printing>-Namespace verweisen.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket und PrintCapabilities  
 Die Klassen <xref:System.Printing.PrintTicket> und <xref:System.Printing.PrintCapabilities> sind die Grundlage der erweiterten XPS-Funktionen. Beide Objekttypen sind XML-formatierte Strukturen von Druck orientierten Features, wie z. b. Sortierung, zweiseitiger Druck, Heftung usw. Diese Strukturen werden durch das Druck Schema definiert. Ein <xref:System.Printing.PrintTicket> weist einen Drucker an, wie ein Druckauftrag verarbeitet werden muss. Die <xref:System.Printing.PrintCapabilities> -Klasse definiert die Fähigkeiten eines Druckers. Durch Abfragen der Funktionen eines Druckers kann ein <xref:System.Printing.PrintTicket> erstellt werden, das die von einem Drucker unterstützten Funktionen in vollem Umfang nutzt. Analog dazu können nicht unterstützte Funktionen vermieden werden.  
  
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
 Ein-<xref:System.Windows.Xps.XpsDocumentWriter>, dessen zahlreiche <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>-und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>-Methoden verwendet werden, um XPS-Dokumente in ein <xref:System.Printing.PrintQueue>zu schreiben. Beispielsweise wird die <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29>-Methode verwendet, um ein XPS-Dokument auszugeben und synchron <xref:System.Printing.PrintTicket>. Die <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29>-Methode wird verwendet, um ein XPS-Dokument auszugeben und asynchron <xref:System.Printing.PrintTicket>.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Xps.XpsDocumentWriter> mithilfe von Code erstellt wird.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methoden stellen ebenfalls Druckmöglichkeiten bereit. Weitere Informationen finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>GDI-Druckpfad  
 Während WPF-Anwendungen den XPS-Druckpfad nativ unterstützen, können Win32-und Windows Forms-Anwendungen auch einige XPS-Funktionen nutzen. Der XPS-Druckertreiber (XPSDrv) kann eine GDI-basierte Ausgabe in das XPS-Format konvertieren. Für erweiterte Szenarien wird die benutzerdefinierte Konvertierung von Inhalten mithilfe von [Microsoft XPS Document Converter (mxdc)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)unterstützt. Ebenso können WPF-Anwendungen auch an den GDI-Druck Pfad ausgeben, indem Sie eine der Methoden <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> oder <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> der Klasse <xref:System.Windows.Xps.XpsDocumentWriter> aufrufen und einen nicht-XPSDrv-Drucker als Ziel Druck Warteschlange festlegen.  

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
  
- **Erweiterte Grafikunterstützung**. Durch die systemeigene Unterstützung von Transparenz und Farbverlaufs primitiven wird die rasterisierung von Inhalten im XPS-Dokument vermieden.  
  
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
- [Gewusst wie-Themen](printing-how-to-topics.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [XPS-Dokumente](/windows/desktop/printdocs/documents)
- [Serialisierung und Speicherung von Dokumenten](document-serialization-and-storage.md)
- [Microsoft XPS Document Converter (mxdc)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
