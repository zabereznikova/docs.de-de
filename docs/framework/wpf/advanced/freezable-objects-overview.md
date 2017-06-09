---
title: "&#220;bersicht &#252;ber Freezable-Objekte | Microsoft Docs"
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
  - "Klassen, Freezable-Objekt"
  - "Freezable-Objekte, description"
  - "Aufheben der Fixierung von Freezable-Objekten"
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# &#220;bersicht &#252;ber Freezable-Objekte
In diesem Thema wird die effektive Verwendung und Erstellung von <xref:System.Windows.Freezable>\-Objekten beschrieben, die besondere Features zur Verbesserung der Anwendungsleistung bereitstellen.  Beispiele für Freezable\-Objekte sind Pinsel, Stifte, Transformationen, Geometrien und Animationen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="whatisafreezable"></a>   
## Was ist ein Freezable\-Objekt?  
 Ein <xref:System.Windows.Freezable> ist ein besonderer Typ von Objekt, das zwei Zustände aufweisen kann: nicht fixiert und fixiert.  Wenn ein <xref:System.Windows.Freezable>\-Objekt nicht fixiert ist, scheint es sich wie jedes andere Objekt zu verhalten.  Ist ein <xref:System.Windows.Freezable>\-Objekt fixiert, kann es nicht mehr geändert werden.  
  
 Ein <xref:System.Windows.Freezable> stellt ein <xref:System.Windows.Freezable.Changed>\-Ereignis bereit, um die Betrachter im Falle von Objektänderungen zu benachrichtigen.  Das Fixieren eines <xref:System.Windows.Freezable>\-Objekts kann zu Leistungsverbesserungen führen, da es keine Ressourcen mehr für Änderungsbenachrichtigungen bindet.  Ein fixiertes <xref:System.Windows.Freezable> kann außerdem über Threads freigegeben werden, während diese Möglichkeit für ein nicht fixiertes <xref:System.Windows.Freezable> nicht besteht.  
  
 Obwohl die <xref:System.Windows.Freezable>\-Klasse viele Anwendungen aufweist, sind die meisten <xref:System.Windows.Freezable>\-Objekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] mit dem Grafiksubsystem verknüpft.  
  
 Die <xref:System.Windows.Freezable>\-Klasse vereinfacht die Verwendung von bestimmten Objekten des Grafiksystems und kann zu einer Verbesserung der Anwendungsleistung beitragen.  Beispiele von Klassentypen, die von <xref:System.Windows.Freezable> erben, sind die Klassen <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform> und <xref:System.Windows.Media.Geometry>.  Da sie nicht verwaltete Ressourcen enthalten, muss das System die Änderungen dieser Objekte überwachen und bei einer Änderung des Originalobjekts die entsprechenden nicht verwalteten Ressourcen aktualisieren.  Auch wenn Sie in Wirklichkeit kein Objekt im Grafiksystem ändern, muss das System für den Fall einer Änderung trotzdem einige seiner Ressourcen zur Überwachung des Objekts binden.  
  
 Angenommen, Sie erstellen einen <xref:System.Windows.Media.SolidColorBrush>\-Pinsel und verwenden ihn, um den Hintergrund einer Schaltfläche zu zeichnen.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Beim Rendern der Schaltfläche verwendet das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Grafiksubsystem die von Ihnen bereitgestellten Informationen, um eine Pixelgruppe zur Erstellung der Schaltflächendarstellung zu zeichnen.  Obwohl Sie anhand des Volltonfarbenpinsels angeben, wie die Schaltfläche gezeichnet werden soll, wird das tatsächliche Zeichnen nicht vom Volltonfarbenpinsel durchgeführt.  Das Grafiksystem generiert für die Schaltfläche und für den Pinsel schnelle, systemnahe Objekte; und genau diese Objekte werden dann auf dem Bildschirm angezeigt.  
  
 Sollten Sie den Pinsel ändern, müssen Sie diese systemnahen Objekte neu generieren.  Die Freezable\-Klasse gibt einem Pinsel die Fähigkeit, die ihm entsprechenden generierten systemnahen Objekte zu finden und sie im Falle einer Änderung zu aktualisieren.  Wenn diese Fähigkeit aktiviert ist, wird der Pinsel als "nicht fixiert" bezeichnet.  
  
 Die <xref:System.Windows.Freezable.Freeze%2A>\-Methode eines Freezable\-Objekts ermöglicht es Ihnen, diese selbstaktualisierende Fähigkeit zu deaktivieren.  Sie können diese Methode verwenden, um den Pinsel zu "fixieren", d. h. als nicht änderbar zu definieren.  
  
> [!NOTE]
>  Nicht jedes Freezable\-Objekt kann fixiert werden.  Um das Auslösen einer <xref:System.InvalidOperationException> zu verhindern, müssen Sie den <xref:System.Windows.Freezable.CanFreeze%2A>\-Eigenschaftswert des Freezable\-Objekts prüfen, um vor dem Fixieren zu ermitteln, ob das Objekt fixiert werden kann.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Wenn Sie ein Freezable\-Objekt nicht mehr ändern müssen, führt das Fixieren des Objekts zu Leistungsvorteilen.  Wenn Sie den Pinsel in diesem Beispiel fixieren würden, müsste das Grafiksystem ihn nicht mehr überwachen, um eventuelle Änderungen zu ermitteln.  Außerdem kann das Grafiksystem andere Optimierungen vornehmen, da es davon ausgehen kann, dass sich der Pinsel nicht ändert.  
  
> [!NOTE]
>  Der Einfachheit halber bleiben Freezable\-Objekte so lange nicht fixiert, bis Sie sie explizit fixieren.  
  
<a name="frozenfreezables"></a>   
## Verwenden von Freezable\-Objekten  
 Ein nicht fixiertes Freezable wird wie jeder andere Objekttyp verwendet.  Im folgenden Beispiel wird die Farbe eines <xref:System.Windows.Media.SolidColorBrush> von Gelb in Rot geändert, nachdem der Pinsel verwendet wurde, um den Hintergrund einer Schaltfläche zu zeichnen.  Das Grafiksystem ändert die Schaltfläche automatisch im Hintergrund von Gelb in Rot, wenn der Bildschirm das nächste Mal aktualisiert wird.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### Fixieren von Freezable\-Objekten  
 Um ein <xref:System.Windows.Freezable> als unveränderlich auszuweisen, rufen Sie seine <xref:System.Windows.Freezable.Freeze%2A>\-Methode auf.  Wenn Sie ein Objekt fixieren, das Freezable\-Objekte enthält, werden diese Objekte ebenfalls fixiert.  Wenn Sie z. B. eine <xref:System.Windows.Media.PathGeometry> fixieren, werden auch die darin enthaltenen Formen und Segmente fixiert.  
  
 Ein Freezable **kann nicht** fixiert werden, wenn einer der folgenden Punkte zutrifft:  
  
-   Es verfügt über animierte oder datengebundene Eigenschaften.  
  
-   Es verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden.  \(Weitere Informationen zu dynamischen Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).\)  
  
-   Es enthält untergeordnete <xref:System.Windows.Freezable>\-Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen nicht zutreffen und Sie das <xref:System.Windows.Freezable>\-Objekt nicht ändern möchten, sollten Sie es fixieren, um die bereits erläuterten Leistungsvorteile zu erzielen.  
  
 Nachdem Sie die <xref:System.Windows.Freezable.Freeze%2A>\-Methode eines Freezable\-Objekts aufgerufen haben, kann es nicht mehr geändert werden.  Der Versuch, ein fixiertes Objekt zu ändern, löst eine <xref:System.InvalidOperationException> aus.  Im folgenden Code wird eine Ausnahme ausgelöst, weil der Versuch unternommen wird, einen bereits fixierten Pinsel zu ändern.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Sie können das Auslösen dieser Ausnahme verhindern, wenn Sie mithilfe der <xref:System.Windows.Freezable.IsFrozen%2A>\-Methode ermitteln, ob das <xref:System.Windows.Freezable>\-Objekt fixiert ist.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Im vorherigen Codebeispiel wurde eine veränderliche Kopie eines fixierten Objekts mithilfe der <xref:System.Windows.Freezable.Clone%2A>\-Methode erstellt.  Ausführliche Informationen zum Klonen finden Sie im nächsten Abschnitt.  
  
 **Hinweis:** Da ein fixiertes Freezable\-Objekt nicht animiert werden kann, erstellt das Animationssystem automatisch veränderliche Klons von fixierten <xref:System.Windows.Freezable>\-Objekten, wenn Sie sie mit einem <xref:System.Windows.Media.Animation.Storyboard> animieren.  Um den durch das Klonen verursachten höheren Leistungsaufwand zu vermeiden, sollten Sie ein zu animierendes Objekt nicht fixieren.  Weitere Informationen über Animationen mit Storyboards finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### Fixieren über Markup  
 Um ein in Markup deklariertes <xref:System.Windows.Freezable>\-Objekt zu fixieren, verwenden Sie das `PresentationOptions:Freeze`\-Attribut.  Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> als Seitenressource deklariert und fixiert.  Danach wird der Pinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Um das `Freeze`\-Attribut verwenden zu können, müssen Sie eine Zuordnung zum Namespace der Präsentationsoptionen vornehmen: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.  `PresentationOptions` ist das empfohlene Präfix für die Zuordnung dieses Namespaces.  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Da nicht alle XAML\-Reader dieses Attribut akzeptieren, sollten Sie das [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) verwenden, um das `Presentation:Freeze`\-Attribut als ignorierbar zu kennzeichnen:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Weitere Informationen finden Sie auf der Seite [mc:Ignorable\-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).  
  
### Aufheben der Fixierung von Freezable\-Objekten  
 Sobald ein <xref:System.Windows.Freezable>\-Objekt fixiert ist, kann es nicht geändert und seine Fixierung nicht aufgehoben werden. Sie können jedoch mit der <xref:System.Windows.Freezable.Clone%2A>\-Methode oder der <xref:System.Windows.Freezable.CloneCurrentValue%2A>\-Methode einen nicht fixierten Klon erstellen.  
  
 Im folgenden Beispiel wird der Hintergrund einer Schaltfläche mit einem Pinsel festgelegt, der daraufhin fixiert wird.  Mithilfe der <xref:System.Windows.Freezable.Clone%2A>\-Methode wird eine nicht fixierte Kopie des Pinsels erstellt.  Der Klon wird geändert und verwendet, um den Hintergrund der Schaltfläche von Gelb in Rot zu ändern.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Unabhängig von der verwendeten Klonmethode werden Animationen nicht in das neue <xref:System.Windows.Freezable>\-Objekt kopiert.  
  
 Die Methoden <xref:System.Windows.Freezable.Clone%2A> und <xref:System.Windows.Freezable.CloneCurrentValue%2A> erstellen tiefe Kopien des Freezable\-Objekts.  Wenn das Freezable\-Objekt weitere fixierte Freezable\-Objekte enthält, werden diese ebenso geklont und als veränderlich ausgewiesen.  Wenn Sie z. B. eine fixierte <xref:System.Windows.Media.PathGeometry> klonen, damit sie geändert werden kann, werden die darin enthaltenen Formen und Segmente ebenfalls kopiert und als veränderlich ausgewiesen.  
  
<a name="createyourownfreezableclass"></a>   
## Erstellen einer eigenen Freezable\-Klasse  
 Eine von <xref:System.Windows.Freezable> abgeleitete Klasse erhält die folgenden Features:  
  
-   Besondere Zustände: ein schreibgeschützter \(fixierter\) Zustand und ein nicht schreibgeschützter Zustand.  
  
-   Threadsicherheit: Ein fixiertes <xref:System.Windows.Freezable>\-Objekt kann über Threads freigegeben werden.  
  
-   Ausführliche Änderungsbenachrichtigung: Im Gegensatz zu einem anderen <xref:System.Windows.DependencyObject> stellt ein Freezable\-Objekt Änderungsbenachrichtigungen bereit, wenn Werte von Untereigenschaften geändert werden.  
  
-   Leichtes Klonen: In der Freezable\-Klasse sind bereits mehrere Methoden implementiert, die tiefe Klone erstellen.  
  
 Ein <xref:System.Windows.Freezable> ist ein <xref:System.Windows.DependencyObject>\-Typ und verwendet demzufolge das Abhängigkeitseigenschaftensystem.  Die Klasseneigenschaften müssen keine Abhängigkeitseigenschaften sein, aber die Verwendung von Abhängigkeitseigenschaften reduziert den Umfang des zu schreibenden Codes, da die <xref:System.Windows.Freezable>\-Klasse unter Berücksichtigung der Abhängigkeitseigenschaften entwickelt wurde.  Weitere Informationen über das Abhängigkeitseigenschaftensystem finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Jede <xref:System.Windows.Freezable>\-Unterklasse muss die <xref:System.Windows.Freezable.CreateInstanceCore%2A>\-Methode überschreiben.  Verwendet die Klasse Abhängigkeitseigenschaften für alle ihre Daten, müssen Sie keine weiteren Maßnahmen ergreifen.  
  
 Wenn die Klasse Datenmember enthält, die keine Abhängigkeitseigenschaften verwenden, müssen Sie außerdem die folgenden Methoden überschreiben:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Beachten Sie außerdem die folgenden Regeln für das Aufrufen von Datenmembern und das Schreiben in Datenmember, bei denen es sich um keine Abhängigkeitseigenschaften handelt:  
  
-   Rufen Sie am Anfang jeder [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], die Datenmember ohne Abhängigkeitseigenschaft abruft, die <xref:System.Windows.Freezable.ReadPreamble%2A>\-Methode auf.  
  
-   Rufen Sie am Anfang jeder API, die Datenmember ohne Abhängigkeitseigenschaft aufzeichnet, die <xref:System.Windows.Freezable.WritePreamble%2A>\-Methode auf.  \(Nachdem Sie die <xref:System.Windows.Freezable.WritePreamble%2A>\-Methode in einer [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] aufgerufen haben, müssen Sie <xref:System.Windows.Freezable.ReadPreamble%2A> nicht zusätzlich aufrufen, wenn Sie auch Datenmember ohne Abhängigkeitseigenschaften abrufen.\)  
  
-   Rufen Sie die <xref:System.Windows.Freezable.WritePostscript%2A>\-Methode vor dem Beenden von Methoden auf, die in Datenmember ohne Abhängigkeitseigenschaften schreiben.  
  
 Wenn die Klasse Datenmember ohne Abhängigkeitseigenschaften enthält, bei denen es sich um <xref:System.Windows.DependencyObject>\-Objekte handelt, müssen Sie außerdem die <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>\-Methode bei jeder Änderung der Werte aufrufen. Dies trifft auch dann zu, wenn Sie den Member auf `null` festlegen.  
  
> [!NOTE]
>  Hierbei ist besonders zu beachten, dass Sie das Überschreiben jeder <xref:System.Windows.Freezable>\-Methode mit dem Aufruf an die Basisimplementierung beginnen.  
  
 Ein Beispiel für eine benutzerdefinierte <xref:System.Windows.Freezable>\-Klasse finden Sie unter [Beispiel für benutzerdefinierte Animation](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## Siehe auch  
 <xref:System.Windows.Freezable>   
 [Beispiel für benutzerdefinierte Animation](http://go.microsoft.com/fwlink/?LinkID=159981)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)