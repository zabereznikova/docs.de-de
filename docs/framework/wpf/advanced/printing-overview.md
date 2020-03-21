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
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187203"
---
# <a name="printing-overview"></a>Übersicht über das Drucken
Mit Microsoft .NET Framework verfügen Anwendungsentwickler, die Windows Presentation Foundation (WPF) verwenden, über einen umfangreichen neuen Satz von Druck- und Drucksystemverwaltungs-APIs. Mit Windows Vista stehen einige dieser Drucksystemerweiterungen auch Entwicklern zur Verfügung, die Windows Forms-Anwendungen erstellen, und Entwicklern, die nicht verwalteten Code verwenden. Kernstück dieser neuen Funktionalität ist das neue XML Paper Specification (XPS)-Dateiformat und der XPS-Druckpfad.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>Info über XPS  
 XPS ist ein elektronisches Dokumentformat, ein Spool-Dateiformat und eine Seitenbeschreibungssprache. Es ist ein offenes Dokumentformat, das XML, Open Packaging Conventions (OPC) und andere Industriestandards verwendet, um plattformübergreifende Dokumente zu erstellen. XPS vereinfacht den Prozess, mit dem digitale Dokumente erstellt, freigegeben, gedruckt, angezeigt und archiviert werden. Weitere Informationen zu XPS finden Sie unter [XPS-Dokumente](/windows/desktop/printdocs/documents).  
  
 In [Programmatisch druckenvon XPS-Dateien](how-to-programmatically-print-xps-files.md)werden verschiedene Techniken zum Drucken von XPS-basierten Inhalten mithilfe von WPF demonstriert. Es kann sinnvoll sein, diese Beispiele beim Durcharbeiten der in diesem Thema enthaltenen Inhalte hinzuzuziehen. (Nicht verwalteter Code sollten die Dokumentation für die [MXDC_ESCAPE-Funktion](/windows/desktop/printdocs/mxdc-escape)sehen. Windows Forms-Entwickler müssen die <xref:System.Drawing.Printing> API im Namespace verwenden, die nicht den vollständigen XPS-Druckpfad unterstützt, aber einen Hybrid-GDI-zu-XPS-Druckpfad unterstützt. Weitere Informationen finden Sie unter **Druckpfadarchitektur** unten.)  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>XPS-Druckpfad  
 Der XML Paper Specification (XPS)-Druckpfad ist eine neue Windows-Funktion, die neu definiert, wie das Drucken in Windows-Anwendungen behandelt wird. Da XPS eine Dokumentpräsentationssprache (z. B. RTF), ein Druckspoolerformat (z. B. WMF) und eine Seitenbeschreibungssprache (z. B. PCL oder Postscript) ersetzen kann; Der neue Druckpfad behält das XPS-Format von der Anwendungspublikation bis zur endgültigen Verarbeitung im Druckertreiber oder Gerät bei.  
  
 Der XPS-Druckpfad basiert auf dem XPS-Druckertreibermodell (XPSDrv), das Entwicklern mehrere Vorteile bietet, wie z. B. WYSIWYG (WYSIWYG) (WYSIWYG), verbesserte Farbunterstützung und deutlich verbesserte Druckleistung. (Weitere Informationen zu XPSDrv finden Sie in der Dokumentation zum [Windows Driver Kit](/windows-hardware/drivers/).)  
  
 Der Betrieb des Druckspoolers für XPS-Dokumente ist im Wesentlichen derselbe wie in früheren Windows-Versionen. Es wurde jedoch verbessert, um den XPS-Druckpfad zusätzlich zum vorhandenen GDI-Druckpfad zu unterstützen. Der neue Druckpfad verbraucht nativ eine XPS-Spooldatei. Während Druckertreiber im Benutzermodus, die für frühere Windows-Versionen geschrieben wurden, weiterhin funktionieren, ist ein XPS-Druckertreiber (XPSDrv) erforderlich, um den XPS-Druckpfad zu verwenden.  
  
 Die Vorteile des XPS-Druckpfads sind erheblich und umfassen:  
  
- WYSIWYG-Druckunterstützung  
  
- Systemeigene Unterstützung für erweiterte Farbprofile, die auch 32 Bit pro Kanal (bpc), CMYK, benannte Farben, n-Tinten und systemeigene Unterstützung von Transparenz und Farbverläufen einschließen.  
  
- Verbesserte Druckleistung für .NET Framework- und Win32-basierte Anwendungen.  
  
- Industriestandard XPS-Format.  
  
 Für grundlegende Druckszenarien steht eine einfache und intuitive API mit einem einzigen Einstiegspunkt für Benutzeroberfläche, Konfiguration und Auftragsübermittlung zur Verfügung. Für erweiterte Szenarien steht jetzt zusätzlich Unterstützung für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Anpassung (oder Verzicht auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), synchronen oder asynchronen Druck und Funktionen zum Druck von Batchaufträgen zur Verfügung. Beide Optionen bieten Druckunterstützung mit vollständigen oder eingeschränkten Vertrauensstellungen.  
  
 XPS wurde unter Berücksichtigung der Erweiterbarkeit entwickelt. Durch die Verwendung des Erweiterbarkeitsframeworks können XPS Funktionen und Funktionen modular hinzugefügt werden. Zu den Erweiterungsfunktionen gehören:  
  
- Druckschema. Das öffentliche Schema wird regelmäßig aktualisiert und ermöglicht die schnelle Erweiterung von Gerätefunktionen. (Siehe dazu **PrintTicket und PrintCapabilities** unten.)  
  
- Erweiterbare Filterpipeline. Die XPS-Filterpipeline (XPSDrv) wurde entwickelt, um sowohl das direkte als auch skalierbare Drucken von XPS-Dokumenten zu ermöglichen. Weitere Informationen finden Sie unter [XPSDrv-Druckertreiber](/windows-hardware/drivers/print/xpsdrv-printer-drivers).
  
### <a name="print-path-architecture"></a>Druckpfadarchitektur  
 Während sowohl Win32- als auch .NET Framework-Anwendungen XPS unterstützen, verwenden Win32- und Windows Forms-Anwendungen eine GDI-in-XPS-Konvertierung, um XPS-formatierte Inhalte für den XPS-Druckertreiber (XPSDrv) zu erstellen. Diese Anwendungen müssen den XPS-Druckpfad nicht verwenden und können weiterhin AUF EMF-basiertem Drucken (Enhanced Metafile) drucken. Die meisten XPS-Funktionen und -Erweiterungen sind jedoch nur für Anwendungen verfügbar, die auf den XPS-Druckpfad abzielen.  
  
 Um die Verwendung von XPSDrv-basierten Druckern durch Win32- und Windows Forms-Anwendungen zu ermöglichen, unterstützt der XPS-Druckertreiber (XPSDrv) die Konvertierung von GDI in das XPS-Format. Das XPSDrv-Modell bietet auch einen Konverter für das XPS-zu-GDI-Format, damit Win32-Anwendungen XPS-Dokumente drucken können. Bei WPF-Anwendungen erfolgt die Konvertierung des XPS-Formats <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> in <xref:System.Windows.Xps.XpsDocumentWriter> das GDI-Format automatisch durch die <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und Methoden der Klasse, wenn die Zieldruckwarteschlange des Schreibvorgangs nicht über einen XPSDrv-Treiber verfügt. (Windows Forms-Anwendungen können XPS-Dokumente nicht drucken.)  
  
 Die folgende Abbildung zeigt das Drucksubsystem und definiert die von Microsoft bereitgestellten Teile sowie die von Software- und Hardwareherstellern definierten Teile:  
  
 ![Screenshot zeigt das XPS-Drucksystem.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Einfacher XPS-Druck  
 WPF definiert sowohl eine grundlegende als auch eine erweiterte API. Für Anwendungen, die keine umfassende Druckanpassung oder keinen Zugriff auf den vollständigen XPS-Funktionssatz erfordern, ist grundlegende Druckunterstützung verfügbar. Die einfache Druckunterstützung wird über ein Druckdialogfeld-Steuerelement verfügbar gemacht, das nur minimale Konfiguration erfordert und eine vertraute [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bietet. Viele XPS-Funktionen sind mit diesem vereinfachten Druckmodell verfügbar.  
  
#### <a name="printdialog"></a>PrintDialog  
 Das <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Steuerelement stellt einen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]einzelnen Einstiegspunkt für die Konfiguration und die XPS-Auftragsübermittlung bereit. Informationen zum Instanziieren und Verwenden des Steuerelements finden Sie unter [Aufrufen eines Druckdialogfelds](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Erweiterter XPS-Druck  
 Um auf den vollständigen Satz von XPS-Funktionen zugreifen zu können, muss die erweiterte Druck-API verwendet werden. Im Folgenden werden mehrere relevante APIs ausführlicher beschrieben. Eine vollständige Liste der XPS-Druckpfad-APIs finden Sie unter die <xref:System.Windows.Xps> und <xref:System.Printing> Namespace-Referenzen.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket und PrintCapabilities  
 Die <xref:System.Printing.PrintTicket> <xref:System.Printing.PrintCapabilities> und Klassen sind die Grundlage der erweiterten XPS-Funktionen. Beide Objekttypen sind XML-formatierte Strukturen druckorientierter Features wie Sortierung, beidseitiges Drucken, Heften usw. Diese Strukturen werden durch das Druckschema definiert. Ein <xref:System.Printing.PrintTicket> weist einen Drucker an, wie ein Druckauftrag verarbeitet werden muss. Die <xref:System.Printing.PrintCapabilities> -Klasse definiert die Fähigkeiten eines Druckers. Durch Abfragen der Funktionen eines Druckers kann ein <xref:System.Printing.PrintTicket> erstellt werden, das die von einem Drucker unterstützten Funktionen in vollem Umfang nutzt. Analog dazu können nicht unterstützte Funktionen vermieden werden.  
  
 Im folgenden Beispiel wird das Abfragen der <xref:System.Printing.PrintCapabilities> eines Druckers und das Erstellen eines <xref:System.Printing.PrintTicket> mithilfe von Code gezeigt.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer und PrintQueue  
 Die <xref:System.Printing.PrintServer>-Klasse stellt einen Netzwerkdruckerserver und die <xref:System.Printing.PrintQueue>-Klasse einen Drucker mit zugeordneter Auftragswarteschlange dar. Zusammen ermöglichen diese APIs eine erweiterte Verwaltung der Druckaufträge eines Servers. Ein <xref:System.Printing.PrintServer> oder eine davon abgeleitete Klasse wird verwendet, um eine <xref:System.Printing.PrintQueue> zu verwalten. Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methode wird verwendet, um einen neuen Druckauftrag in die Warteschlange einzustellen.  
  
 Das folgende Beispiel zeigt, wie ein <xref:System.Printing.LocalPrintServer> erstellt und mithilfe von Code auf seine Standard-<xref:System.Printing.PrintQueue> zugegriffen wird.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Eine <xref:System.Windows.Xps.XpsDocumentWriter>wird verwendet, <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> um XPS-Dokumente in eine <xref:System.Printing.PrintQueue>zu schreiben. Die <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> Methode wird z. B. zum <xref:System.Printing.PrintTicket> Ausgeben eines XPS-Dokuments und synchron verwendet. Die <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> Methode wird verwendet, um <xref:System.Printing.PrintTicket> ein XPS-Dokument auszugeben und asynchron.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Xps.XpsDocumentWriter> mithilfe von Code erstellt wird.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Die <xref:System.Printing.PrintQueue.AddJob%2A>-Methoden stellen ebenfalls Druckmöglichkeiten bereit. Weitere Informationen finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md). .  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>GDI-Druckpfad  
 Während WPF-Anwendungen nativ den XPS-Druckpfad unterstützen, können Win32- und Windows Forms-Anwendungen auch einige XPS-Funktionen nutzen. Der XPS-Druckertreiber (XPSDrv) kann gDI-basierte Ausgabe in das XPS-Format konvertieren. Für erweiterte Szenarien wird die benutzerdefinierte Konvertierung von Inhalten mit dem [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)unterstützt. In ähnlicher Weise können WPF-Anwendungen auch an den <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> GDI-Druckpfad ausgegeben werden, indem sie eine der oder <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter> Klasse aufrufen und einen Nicht-XpsDrv-Drucker als Zieldruckwarteschlange bezeichnen.  

Bei Anwendungen, die keine XPS-Funktionalität oder -Unterstützung benötigen, bleibt der aktuelle GDI-Druckpfad unverändert.  
  
- Weitere Referenzmaterialien zum GDI-Druckpfad und den verschiedenen XPS-Konvertierungsoptionen finden Sie unter [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) und [XPSDrv Printer Drivers](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>XPSDrv-Treibermodell  
 Der XPS-Druckpfad verbessert die Spoolereffizienz, indem XPS als natives Druckspoolformat beim Drucken auf einem XPS-fähigen Drucker oder Treiber verwendet wird. Der vereinfachte Spooling-Prozess macht es überflüssig, eine Zwischenspooldatei, z. B. eine EMF-Datendatei, zu generieren, bevor das Dokument gepoolt wird. Durch kleinere Spooldateigrößen kann der XPS-Druckpfad den Netzwerkverkehr reduzieren und die Druckleistung verbessern.  
  
 EMF ist ein geschlossenes Format, das die Anwendungsausgabe als eine Reihe von Aufrufen in GDI zum Rendern von Diensten darstellt. Im Gegensatz zu EMF stellt das XPS-Spoolformat das eigentliche Dokument dar, ohne dass bei der Ausgabe an einen XPS-basierten Druckertreiber (XPSDrv) weitere Interpretationen erforderlich sind. Die Treiber können direkt mit den Daten im vorliegenden Format arbeiten. Mit dieser Funktion werden die Daten- und Farbraumkonvertierungen entfernt, die erforderlich sind, wenn Sie EMF-Dateien und GDI-basierte Druckertreiber verwenden.  
  
 Spooldateigrößen werden in der Regel reduziert, wenn Sie XPS-Dokumente verwenden, die auf einen XPS-Druckertreiber (XPSDrv) im Vergleich zu ihren EMF-Äquivalenten abzielen. Es gibt jedoch Ausnahmen:  
  
- Eine Vektorgrafik, die sehr komplex ist, viele Ebenen aufweist oder ineffizient geschrieben wurde, kann größer als die Bitmapversion der gleichen Grafik sein.  
  
- Zum Zweck der Anzeige am Bildschirm werden in XPS-Dateien Geräteschriftarten sowie computerbasierte Schriftarten eingebettet, während in GDI-Spooldateien keine Geräteschriftarten eingebettet sind. Beide Schriftarten sind jedoch in Teilmengen gegliedert (siehe unten), und Druckertreiber können die Geräteschriftarten vor der Übertragung der Datei an den Drucker entfernen.  
  
 Die Reduzierung der Spoolgröße erfolgt mithilfe mehrerer Mechanismen:  
  
- **Unterklassen von Schriftarten**. Nur Zeichen, die im eigentlichen Dokument verwendet werden, werden in der XPS-Datei gespeichert.  
  
- **Erweiterte Grafikunterstützung**. Die native Unterstützung für Transparenz- und Gradientenprimitive vermeidet die Rasterung von Inhalten im XPS-Dokument.  
  
- **Erkennung gemeinsamer Ressourcen**. Ressourcen, die mehrfach verwendet werden (wie etwa ein Bild, das ein Firmenlogo darstellt) werden als freigegebene Ressourcen behandelt und nur einmal geladen.  
  
- **ZIP-Komprimierung**. Alle XPS-Dokumente verwenden ZIP-Komprimierung.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [How-to-Themen](printing-how-to-topics.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [XPS-Dokumente](/windows/desktop/printdocs/documents)
- [Serialisierung und Speicherung von Dokumenten](document-serialization-and-storage.md)
- [Microsoft XPS-Dokumentkonverter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
