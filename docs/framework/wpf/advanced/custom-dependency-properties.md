---
title: "Benutzerdefinierte Abhängigkeitseigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1ee7c7b4e21d147bad1cd8e4b854c0ff4fe13aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-dependency-properties"></a>Benutzerdefinierte Abhängigkeitseigenschaften
Dieses Thema beschreibt die Gründe, warum Anwendungsentwickler und Komponentenautoren in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] benutzerdefinierte Abhängigkeitseigenschaften erstellen möchten, und beschreibt die Implementierungsmaßnahmen und -optionen, die die Leistung, Verwendbarkeit oder Vielseitigkeit der Eigenschaft verbessern können.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht von vorhandenen Abhängigkeitseigenschaften von Consumern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen auskennen, und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vertraut sein und wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen geschrieben werden.  
  
<a name="whatis"></a>   
## <a name="what-is-a-dependency-property"></a>Was ist eine Abhängigkeitseigenschaft?  
 Sie können eine Eigenschaft aktivieren, die normalerweise eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft wäre, um die Verwendung von Stilen, Datenbindung, Vererbung, Animationen und Standardwerten zu unterstützen, indem Sie sie als Abhängigkeitseigenschaft implementieren. Abhängigkeitseigenschaften sind Eigenschaften, die registriert werden die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> Methode (oder <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>), und, die gesichert werden, von einer <xref:System.Windows.DependencyProperty> Bezeichnerfeld. Abhängigkeitseigenschaften genutzt werden nur von <xref:System.Windows.DependencyObject> Typen, aber <xref:System.Windows.DependencyObject> ist sehr hoch ist, in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassenhierarchie, damit die Mehrzahl der in verfügbaren Klassen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Abhängigkeitseigenschaften unterstützen kann. Weitere Informationen zu Abhängigkeitseigenschaften und zur Terminologie und den Konventionen für die Beschreibung in [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="example_dp"></a>   
## <a name="examples-of-dependency-properties"></a>Beispiele für Abhängigkeitseigenschaften  
 Beispiele für Abhängigkeitseigenschaften, die auf implementiert werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen beinhalten die <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft, die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft, und die <xref:System.Windows.Controls.TextBox.Text%2A> a.-Eigenschaft. Jede Abhängigkeitseigenschaft, die von einer Klasse verfügbar gemacht werden, wurde ein entsprechendes öffentliche statisches Feld des Typs <xref:System.Windows.DependencyProperty> für dieselbe Klasse verfügbar gemacht werden. Es handelt sich um den Bezeichner für die Abhängigkeitseigenschaft. Der Name des Bezeichners wird nach einer Konvention gewählt: Der Name der Abhängigkeitseigenschaft mit der angefügten Zeichenfolge `Property`. Z. B. das entsprechende <xref:System.Windows.DependencyProperty> Bezeichnerfeld für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist <xref:System.Windows.Controls.Control.BackgroundProperty>. Der Bezeichner speichert die Informationen über die Abhängigkeitseigenschaft an, wie er registriert wurde, und der Bezeichner wird dann später für andere Vorgänge im Zusammenhang mit der Abhängigkeitseigenschaft, wie ein Aufruf verwendet <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
 Wie in [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) erwähnt, sind alle Abhängigkeitseigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (mit Ausnahme der meisten angefügten Eigenschaften) aufgrund der „Wrapper“-Implementierung auch [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaften. Daher können Sie über Code Abhängigkeitseigenschaften abrufen oder festlegen, indem Sie [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Accessoren aufrufen, die die Wrapper in der Art definieren, in der Sie auch andere [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaften verwenden würden. Als Consumer eingerichteter Abhängigkeitseigenschaften, Sie in der Regel verwenden Sie nicht die <xref:System.Windows.DependencyObject> Methoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A>, wobei es sich um den Verbindungspunkt mit dem zugrunde liegenden Eigenschaftensystem. Vielmehr die vorhandene Implementierung von der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaften haben bereits aufgerufen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> innerhalb der `get` und `set` Wrapperimplementierungen der Eigenschaft, verwenden entsprechend des ID-Felds . Wenn Sie eine benutzerdefinierte Abhängigkeitseigenschaft selbst implementieren, definieren Sie den Wrapper auf ähnliche Weise.  
  
<a name="backing_with_dp"></a>   
## <a name="when-should-you-implement-a-dependency-property"></a>Wann sollten Sie eine Abhängigkeitseigenschaft implementieren?  
 Wenn Sie eine Eigenschaft für eine Klasse implementieren, solange Ihre Klasse abgeleitet <xref:System.Windows.DependencyObject>, haben Sie die Möglichkeit, die Eigenschaft mit einem <xref:System.Windows.DependencyProperty> Bezeichner und somit um eine Abhängigkeitseigenschaft zu machen. Es ist nicht immer notwendig oder angemessen, Ihre Eigenschaft in eine Abhängigkeitseigenschaft umzuwandeln. Es hängt von den Anforderungen Ihres Szenarios ab. Manchmal ist die normale Technik des Sicherns der Eigenschaft mit einem privaten Feld ausreichend. Sie sollten Ihre Eigenschaft allerdings als Abhängigkeitseigenschaft implementieren, wenn Sie möchten, dass Ihre Eigenschaft eine oder mehrere der folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen unterstützt:  
  
-   Sie möchten, dass Ihre Eigenschaft in einem Stil festgelegt werden kann. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
-   Sie möchten, dass die Eigenschaft Datenbindung unterstützt. Weitere Informationen zur Datenbindung mit Abhängigkeitseigenschaften finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).  
  
-   Sie möchten, dass die Eigenschaft mit einem dynamischen Ressourcenverweis festgelegt werden kann. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Sie möchten einen Eigenschaftswert automatisch von einem übergeordneten Element in der Elementstruktur erben. In diesem Fall registrieren mit dem <xref:System.Windows.DependencyProperty.RegisterAttached%2A> -Methode, auch wenn Sie auch einen Eigenschaftenwrapper für erstellen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Zugriff. Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Sie möchten, dass Ihre Eigenschaft animiert werden kann. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Sie möchten, dass das Eigenschaftensystem berichtet, wenn der vorherige Wert der Eigenschaft durch Aktionen des Eigenschaftensystems, der Umgebung, des Benutzers oder durch Lesen und Verwenden von Stilen geändert wurde. Mithilfe von Eigenschaftenmetadaten kann Ihre Eigenschaft eine Rückrufmethode angeben, die jedes Mal aufgerufen wird, wenn das Eigenschaftensystem feststellt, dass der Eigenschaftswert eindeutig geändert wurde. Ein verwandtes Konzept ist die Koersion des Eigenschaftswerts. Weitere Informationen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Sie möchten geltende Konventionen für Metadaten verwenden, die auch von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Vorgängen verwendet werden, z.B. der Bericht, ob das Layoutsystem aufgrund eines geänderten Eigenschaftswerts die visuellen Objekte für ein Element neu aufbauen soll. Oder Sie möchten Überschreibungen von Metadaten verwenden, sodass abgeleitete Klassen auf Metadaten basierende Eigenschaften, z.B. den Standardwert, ändern können.  
  
-   Sie möchten, dass Eigenschaften von benutzerdefinierten Steuerelementen Unterstützung von [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] erhalten, z.B. das Bearbeiten des Fensters **Eigenschaften**. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Wenn Sie diese Szenarios untersuchen, sollten Sie auch bedenken, ob Sie Ihr Szenario erreichen können, indem Sie die Metadaten einer vorhandenen Abhängigkeitseigenschaft überschreiben, anstatt eine völlig neue Eigenschaft zu implementieren. Ob die Überschreibung von Metadaten sinnvoll ist hängt von Ihrem Szenario ab und wie sehr dieses Szenario der Implementierung vorhandener [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Abhängigkeitseigenschaften und -Klassen ähnelt. Weitere Informationen zum Überschreiben der Metadaten von vorhandenen Eigenschaften finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="checklist"></a>   
## <a name="checklist-for-defining-a-dependency-property"></a>Prüfliste für die Definition einer Abhängigkeitseigenschaft  
 Das Definieren einer Abhängigkeitseigenschaft besteht aus vier unterschiedlichen Konzepten. Diese Konzepte sind nicht unbedingt aufeinanderfolgende Schritte, da einige von ihnen am Ende als einzelne Codezeilen in der Implementierung kombiniert werden:  
  
-   (Optional) Erstellen Sie Eigenschaftsmetadaten für die Abhängigkeitseigenschaft.  
  
-   Registrieren Sie den Eigenschaftennamen im Eigenschaftensystem, indem Sie einen Besitzertyp und den Typ des Eigenschaftswerts angeben. Geben Sie, falls verwendet, auch die Metadaten der Eigenschaft an.  
  
-   Definieren einer <xref:System.Windows.DependencyProperty> Bezeichner als eine `public` `static` `readonly` Feld für den Besitzertyp.  
  
-   Definieren Sie eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-„Wrapper“-Eigenschaft, deren Name mit dem Namen der Abhängigkeitseigenschaft übereinstimmt. Implementieren Sie die `get`- und `set`-Accessoren der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-„Wrapper“-Eigenschaft, um eine Verbindung mit der Abhängigkeitseigenschaft herzustellen, die sie sichert.  
  
<a name="registering"></a>   
### <a name="registering-the-property-with-the-property-system"></a>Registrieren der Eigenschaft im Eigenschaftensystem  
 Damit Ihre Eigenschaft zu einer Abhängigkeitseigenschaft wird, müssen Sie diese Eigenschaft in einer Tabelle im Eigenschaftensystem registrieren und einen eindeutigen Bezeichner angeben. Dieser wird als Qualifizierer für spätere Vorgänge im Eigenschaftensystem verwendet. Bei diesen Vorgängen kann es sich um interne Vorgänge oder um Ihr eigenes durch Code aufgerufenes Eigenschaftensystem [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] handeln. Um die Eigenschaft zu registrieren, rufen Sie die <xref:System.Windows.DependencyProperty.Register%2A> Methode innerhalb des Texts der Klasse (innerhalb der Klasse, aber außerhalb von Memberdefinitionen). Das ID-Feld ebenfalls bereitgestellt wird, indem Sie die <xref:System.Windows.DependencyProperty.Register%2A> -Methodenaufruf, als Rückgabewert. Der Grund, die die <xref:System.Windows.DependencyProperty.Register%2A> Aufruf erfolgt außerhalb von anderen Member Definitionen ist, da Sie mithilfe dieser Rückgabewert zuzuweisen und zu erstellen eine `public` `static` `readonly` Feld des Typs <xref:System.Windows.DependencyProperty> als Teil der Klasse. Das Feld wird zum Bezeichner für Ihre Abhängigkeitseigenschaft.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### <a name="dependency-property-name-conventions"></a>Namenskonventionen für Abhängigkeitseigenschaften  
 Es gibt Namenskonventionen für Abhängigkeitseigenschaften, die Sie bis auf bestimmte Ausnahmefälle befolgen müssen.  
  
 Die Abhängigkeitseigenschaft selbst hat einen einfachen Namen, "AquariumGraphic" wie in diesem Beispiel wird als der erste Parameter angegeben ist <xref:System.Windows.DependencyProperty.Register%2A>. Dieser Name muss innerhalb jedes Registrierungstyps eindeutig sein. Abhängigkeitseigenschaften, die über Basistypen geerbt werden, gelten bereits als teil des Registrierungstyps. Namen von geerbten Eigenschaften können nicht erneut registriert werden. Es gibt jedoch ein Verfahren zum Hinzufügen von Klassen als Besitzer einer Abhängigkeitseigenschaft, sogar wenn diese Abhängigkeitseigenschaft nicht geerbt ist. Weitere Informationen hierzu finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Geben Sie einem Bezeichnerfeld beim Erstellen den Namen der Eigenschaft bei der Registrierung und das Suffix `Property`. Dieses Feld ist der Bezeichner für die Abhängigkeitseigenschaft, und es werden später verwendet, als Eingabe für die <xref:System.Windows.DependencyObject.SetValue%2A> und <xref:System.Windows.DependencyObject.GetValue%2A> Sie in den Wrapper durch anderen Codezugriff auf die Eigenschaft durch Ihren eigenen Code von externem Codezugriff Sie nehmen Aufrufe zu ermöglichen , von dem Eigenschaftensystem, und potenziell [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessoren.  
  
> [!NOTE]
>  Die übliche Implementierung ist das Definieren der Abhängigkeitseigenschaft im Text einer Klasse. Es ist aber auch möglich, eine Abhängigkeitseigenschaft im statischen Konstruktor der Klasse zu definieren. Diese Vorgehensweise kann sinnvoll sein, wenn Sie mehr als eine Codezeile benötigen, um die Abhängigkeitseigenschaft zu initialisieren.  
  
<a name="wrapper1"></a>   
### <a name="implementing-the-wrapper"></a>Implementieren des „Wrappers“  
 Die Wrapperimplementierung sollten Aufrufen <xref:System.Windows.DependencyObject.GetValue%2A> in der `get` Implementierung und <xref:System.Windows.DependencyObject.SetValue%2A> in die `set` Implementierung (den ursprünglichen Registrierungsaufruf und das Feld sind hier dargestellt zu aus Gründen der Klarheit).  
  
 In Ausnahmefällen abgesehen, sollten Ihre Wrapperimplementierungen von nur Ausführen der <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> Aktionen bzw. Der Grund hierfür wird im Thema [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md) erläutert.  
  
 Alle vorhandenen öffentlichen Abhängigkeitseigenschaften, die für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Klassen zur Verfügung stehen, verwenden dieses einfache Modell der Wrapper-Implementierung. Ein Großteil der komplexen Funktionsweise von Abhängigkeitseigenschaften ist entweder ein grundsätzliches Verhalten des Eigenschaftensystems oder wird durch andere Konzepte wie Koersion oder Rückrufe für Eigenschaftenänderungen durch Eigenschaftenmetadaten implementiert.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 Erneut, gemäß der Konvention werden der Name der Wrappereigenschaft muss identisch mit dem Namen ausgewählt und als ersten Parameter der <xref:System.Windows.DependencyProperty.Register%2A> Aufruf, der die Eigenschaft registriert. Wenn die Eigenschaft den Konventionen nicht folgt, werden dadurch nicht unbedingt alle möglichen Verwendungsarten deaktiviert, aber Sie werden mehrere deutliche Probleme bemerken:  
  
-   Bestimmte Aspekte von Stilen und Vorlagen funktionieren nicht.  
  
-   Die meisten Tools und Designer verlassen sich auf Benennungskonventionen, um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ordnungsgemäß zu serialisieren oder um Unterstützung für eine Entwicklerumgebung auf Ebene einzelner Eigenschaften zu bieten.  
  
-   Die aktuelle Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ladeprogramms umgeht die Wrapper komplett und verlässt sich beim Verarbeiten von Attributwerten auf die Benennungskonvention. Weitere Informationen finden Sie unter [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
<a name="metadata"></a>   
### <a name="property-metadata-for-a-new-dependency-property"></a>Eigenschaftsmetadaten für eine neue Abhängigkeitseigenschaft  
 Wenn Sie eine Abhängigkeitseigenschaft registrieren, wird bei der Registrierung über das Eigenschaftensystem ein Metadatenobjekt erstellt, das Merkmale der Eigenschaft speichert. Viele dieser Merkmale haben Standardwerte, die festgelegt werden, wenn die Eigenschaft, mit der einfachen Signaturen von registriert ist <xref:System.Windows.DependencyProperty.Register%2A>. Andere Signaturen von <xref:System.Windows.DependencyProperty.Register%2A> ermöglichen es Ihnen, die Metadaten angeben, wie Sie die Eigenschaft registriert werden sollen. Die häufigste Art von Metadaten für Abhängigkeitseigenschaften ist ein Standardwert, der für jede neue Instanz angegeben wird, die diese Eigenschaft verwendet.  
  
 Wenn Sie eine Abhängigkeitseigenschaft erstellen, auf eine abgeleitete Klasse von <xref:System.Windows.FrameworkElement>, können Sie die spezialisiertere Metadatenklasse <xref:System.Windows.FrameworkPropertyMetadata> anstelle der Base <xref:System.Windows.PropertyMetadata> Klasse. Der Konstruktor für die <xref:System.Windows.FrameworkPropertyMetadata> -Klasse verfügt über mehrere Signaturen, die in dem Sie verschiedene Metadatenmerkmale in Kombination angeben können. Wenn Sie nur den Standardwert angeben möchten, verwenden Sie die Signatur, die einen einzelnen Parameter vom Typ akzeptiert <xref:System.Object>. Übergeben Sie diesen Objektparameter typspezifischen Wert als Standardwert für die Eigenschaft (der bereitgestellten Standardwert muss den Typ, die Sie als bereitgestellt werden die `propertyType` Parameter in der <xref:System.Windows.DependencyProperty.Register%2A> aufrufen).  
  
 Für <xref:System.Windows.FrameworkPropertyMetadata>, Sie können auch Metadaten Optionsflags für die Eigenschaft angeben. Diese Flags werden nach der Registrierung in diskrete Eigenschaften auf den Eigenschaftenmetadaten konvertiert und werden verwendet, um bestimmte Bedingungen an andere Prozesse zu kommunizieren, z.B. an das Layoutmodul.  
  
#### <a name="setting-appropriate-metadata-flags"></a>Festlegen von Flags für die entsprechenden Metadaten  
  
-   Wenn Ihre Eigenschaft (oder Änderungen in seinem Wert) wirkt sich auf die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], und insbesondere wirkt sich auf das Layoutsystem sollte der Größe oder das Element auf einer Seite rendern festlegen eine oder mehrere der folgenden Flags: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>Gibt an, dass eine Änderung an dieser Eigenschaft eine Änderung erfordert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Rendering, in denen des enthaltenden Objekts möglicherweise mehr oder weniger Speicherplatz innerhalb des übergeordneten Elements. Für die Eigenschaft „Breite“ sollte beispielsweise dieses Flag festgelegt sein.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>Gibt an, dass eine Änderung an dieser Eigenschaft eine Änderung erfordert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rendern, die in der Regel erfordert eine Änderung in der dedizierten Speicherplatz, aber gibt an, dass die Position innerhalb des Bereichs geändert hat. Für die Eigenschaft „Ausrichtung“ sollte beispielsweise dieses Flag festgelegt sein.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>Gibt an, dass eine andere Änderung, die aufgetreten ist keine Auswirkung auf Layout und die Measures, benötigt jedoch ein weiteres Rendering. Ein Beispiel wäre eine Eigenschaft, die eine Farbe eines vorhandenen Elements ändert, z.B. „Hintergrund“.  
  
    -   Diese Flags werden in Metadaten häufig als ein Protokoll für Ihre eigenen Überschreibungsimplementierungen von Eigenschaftensystem oder Layoutrückrufen verwendet. Möglicherweise z. B. ein <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> Rückruf, der angerufen <xref:System.Windows.UIElement.InvalidateArrange%2A> Wenn eine Eigenschaft der Instanz Änderung eines Werts meldet und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> als `true` in seinen Metadaten.  
  
-   Manche Eigenschaften können Auswirkungen auf die Merkmale des Renderings des übergeordneten Elements haben, sowohl über und unter den Änderungen der oben genannten benötigten Größe. Ein Beispiel ist die <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> Eigenschaft verwendet des flussdokumentmodells, in dem Änderungen an dieser Eigenschaft das gesamte Rendering der Flussdokument ändern können, das den Absatz enthält. Verwendung <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> oder <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> in eigene Eigenschaften ähnliche Fälle zu identifizieren.  
  
-   Standardmäßig unterstützen Abhängigkeitseigenschaften die Datenbindung. Sie können die Datenbindung in Fällen bewusst deaktivieren, in denen kein realistisches Szenario für die Datenbindung besteht, oder in denen die Leistung der Datenbindung für ein großes Objekt als Problem erkannt wird.  
  
-   Standardmäßig wird die Datenbindung <xref:System.Windows.Data.Binding.Mode%2A> für Abhängigkeit Eigenschaften standardmäßig <xref:System.Windows.Data.BindingMode.OneWay>. Sie können immer die Bindung zu ändern <xref:System.Windows.Data.BindingMode.TwoWay> pro Bindungsinstanz; Weitere Informationen finden Sie unter [Geben Sie die Richtung der Bindung](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md). Aber der Autor des Abhängigkeit, Sie können auswählen, dass die Eigenschaft <xref:System.Windows.Data.BindingMode.TwoWay> Bindungsmodus standardmäßig. Ist ein Beispiel für eine vorhandene Abhängigkeitseigenschaft <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>; das Szenario für diese Eigenschaft ist, die die <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> festlegen Logik und die Zusammensetzung des <xref:System.Windows.Controls.MenuItem> interagieren Sie mit der Standardformatvorlage für das Design. Die <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> Eigenschaft Logik verwendet die Datenbindung systemintern, um den Status der Eigenschaft in Übereinstimmung mit anderen Eigenschaften des und Methodenaufrufen beibehalten. Ein anderes Beispieleigenschaft, die bindet <xref:System.Windows.Data.BindingMode.TwoWay> standardmäßig <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>.  
  
-   Sie können auch die Vererbung von Eigenschaften in einer benutzerdefinierten Abhängigkeitseigenschaft aktivieren, durch Festlegen der <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> Flag. Eigenschaftenvererbung eignet sich für ein Szenario, in dem übergeordnete und untergeordnete Elemente über eine gemeinsame Eigenschaft verfügen und es sinnvoll ist, dass das untergeordnete Element diesen bestimmten Eigenschaftswert auf den gleichen Wert wie das übergeordnete Element festlegt. Eine Beispiel-Eigenschaft vererbbar ist <xref:System.Windows.FrameworkElement.DataContext%2A>, die zum Binden von Operationen So aktivieren Sie das wichtige Master / Detail-Szenario für die Darstellung von Daten verwendet wird. Indem Sie die Verfügbarkeit <xref:System.Windows.FrameworkElement.DataContext%2A> vererbbar ist, alle untergeordneten Elemente erben diese auch Datenkontext. Aufgrund der Vererbung von Eigenschaftswerten können Sie einen Datenkontext am Seiten- oder Anwendungsstamm angeben, und müssen ihn nicht für Bindungen in allen möglichen untergeordneten Elementen neu angeben. <xref:System.Windows.FrameworkElement.DataContext%2A>ist auch ein gutes Beispiel verdeutlichen, dass die Vererbung überschreibt den Standardwert, aber es kann immer festgelegt werden lokal auf einem bestimmten untergeordneten Element. Weitere Informationen finden Sie unter [verwenden Sie das Master / Detail-Muster mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). Die Vererbung von Eigenschaftswerten kann zu Leistungseinbußen führen und sollte deswegen nur sparsam eingesetzt werden. Weitere Informationen hierzu finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Legen Sie die <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> Kennzeichen, das angibt, ob die Abhängigkeitseigenschaft erkannt oder von Navigation Journaling Diensten verwendet werden soll. Ein Beispiel ist die <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> Eigenschaft; beliebiges Element in einer Markierung ausgewählt Steuerelement beibehalten werden soll, wenn das Journaling Verlauf navigiert wird.  
  
<a name="RODP"></a>   
## <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften  
 Sie können eine Abhängigkeitseigenschaft definieren, die schreibgeschützt ist. Allerdings unterscheiden sich die Szenarios, warum Sie eine Eigenschaft als schreibgeschützt definieren sollen. Dies ist auch beim Registrieren mit dem Eigenschaftensystem und Verfügbar machen des Bezeichners der Fall. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
<a name="CTDP"></a>   
## <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp  
 Bei Abhängigkeitseigenschaften vom Auflistungstyp gibt es zusätzliche Implementierungsprobleme, die man berücksichtigen sollte. Weitere Informationen finden Sie unter [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md).  
  
<a name="SecurityC"></a>   
## <a name="dependency-property-security-considerations"></a>Überlegungen zur Sicherheit von Abhängigkeitseigenschaften  
 Abhängigkeitseigenschaften sollten als öffentliche Eigenschaften deklariert werden. Bezeichnerfelder für Abhängigkeitseigenschaften sollten als öffentliche statische Felder deklariert werden. Auch wenn Sie versuchen, andere Zugriffsebenen zu deklarieren (z.B. geschützt), kann auf eine Abhängigkeitseigenschaft über den Bezeichner in Kombination mit dem Eigenschaftensystem [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zugegriffen werden. Sogar auf ein geschütztes Bezeichnerfeld ist aufgrund Metadaten Berichts- oder Wert Ermittlung potenziell zugegriffen werden [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] , wie z. B. sind Teil des Systems Eigenschaft <xref:System.Windows.LocalValueEnumerator>. Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
<a name="DPCtor"></a>   
## <a name="dependency-properties-and-class-constructors"></a>Abhängigkeitseigenschaften und Klassenkonstruktoren  
 Es ist ein allgemeines Prinzip für das Programmieren von verwaltetem Code (oft durch Codeanalysetools wie FxCop erzwungen), dass Klassenkonstruktoren keine virtuellen Methoden aufrufen dürfen. Der Grund hierfür ist, dass Konstruktoren als Basisinitialisierung eines abgeleiteten Klassenkonstruktors aufgerufen werden können. Außerdem erfolgt der Eintritt in die virtuelle Methode über den Konstruktor möglicherweise bei einem unvollständigen Initialisierungszustand der erstellten Objektinstanz. Beim Ableiten von einer Klasse, die bereits abgeleitet <xref:System.Windows.DependencyObject>, sollten Sie bedenken, dass im Eigenschaftensystem selbst aufruft und virtuelle Methoden intern verfügbar macht. Diese virtuellen Methoden sind Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dienste für das Eigenschaftensystem. Das Überschreiben der Methoden ermöglicht abgeleiteten Klassen,beim Festlegen von Werten teilzunehmen. Sie sollten die Werte der Abhängigkeitseigenschaft innerhalb von Klassenkonstruktoren nicht festlegen, solange Sie keinem sehr spezifischen Konstruktormuster folgen, um potentielle Probleme bei der Initialisierung der Runtime zu vermeiden. Weitere Informationen finden Sie unter [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Laden von XAML und Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)  
 [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
