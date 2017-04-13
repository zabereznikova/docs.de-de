---
title: "R&#252;ckrufe und Validierung von Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
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
  - "Rückrufe, Überprüfung"
  - "coerce-Wert-Rückrufe"
  - "Abhängigkeitseigenschaften, Rückrufe"
  - "Abhängigkeitseigenschaften, Überprüfung"
  - "Überprüfung von Abhängigkeitseigenschaften"
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# R&#252;ckrufe und Validierung von Abh&#228;ngigkeitseigenschaften
In diesem Thema wird erläutert, wie Abhängigkeitseigenschaften unter Verwendung alternativer benutzerdefinierter Implementierungen für eigenschaftsbezogene Features erstellt werden, z. B. Validierungsbestimmung, Rückrufe, die aufgerufen werden, wenn der effektive Wert der Eigenschaft geändert wird, und das Überschreiben möglicher äußerer Einflüsse auf die Wertbestimmung.  In diesem Thema werden auch Szenarien diskutiert, bei denen eine Erweiterung der Standardsystemverhaltensweisen von Eigenschaften mithilfe dieser Verfahren angemessen ist.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie mit den grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft und dem Anwenden von Metadaten auf eine benutzerdefinierte Abhängigkeitseigenschaft vertraut sind.  Weitere Informationen dazu finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="Validation_Callbacks"></a>   
## Validierungsrückrufe  
 Einer Abhängigkeitseigenschaft können beim ersten Registrieren Validierungsrückrufe zugewiesen werden.  Der Validierungsrückruf ist nicht Teil der Eigenschaftenmetadaten; er ist eine direkte Eingabe der <xref:System.Windows.DependencyProperty.Register%2A>\-Methode.  Daher kann ein Validierungsrückruf nicht durch eine neue Implementierung überschrieben werden, nachdem er für eine Abhängigkeitseigenschaft erstellt wurde.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Die Rückrufe werden so implementiert, dass ein Objektwert für sie bereitgestellt wird.  Sie geben `true` zurück, wenn der bereitgestellte Wert für die Eigenschaft gültig ist. Andernfalls geben sie `false` zurück.  Es wird angenommen, dass die Eigenschaft den richtigen Typ entsprechend dem für das Eigenschaftensystem registrierten Typ hat. Daher wird der Typ innerhalb der Rückrufe normalerweise nicht überprüft.  Die Rückrufe werden vom Eigenschaftensystem bei einer Vielzahl verschiedener Vorgänge verwendet.  Dazu gehören die anfängliche Typinitialisierung nach Standardwert, programmgesteuerte Änderungen durch das Aufrufen von <xref:System.Windows.DependencyObject.SetValue%2A> oder Versuche, die Metadaten mit dem neuen angegebenen Standardwert zu überschreiben.  Wenn der Validierungsrückruf durch einen dieser Vorgänge aufgerufen wird und `false` zurückgibt, wird eine Ausnahme ausgelöst.  Anwendungsentwickler müssen auf die Behandlung solcher Ausnahmen vorbereitet sein.  Validierungsrückrufe werden häufig verwendet, um Enumerationswerte zu validieren oder integer\- und double\-Werte einzuschränken, wenn die Eigenschaft Messungen festlegt, die größer oder gleich null sein müssen.  
  
 Validierungsrückrufe sind speziell zur Klassenvalidierung und nicht zur Instanzvalidierung gedacht.  Die Parameter des Rückrufs geben kein spezifisches <xref:System.Windows.DependencyObject> an, das für die zu validierenden Eigenschaften festgelegt sind.  Daher eignen sich Validierungsrückrufe nicht dazu, mögliche "Abhängigkeiten" zu erzwingen, die einen Eigenschaftswert beeinflussen könnten, wenn der instanzspezifische Wert einer Eigenschaft abhängig von Faktoren wie den instanzspezifischen Werten anderer Eigenschaften oder dem Laufzeitzustand ist.  
  
 Der folgende Beispielcode zeigt ein sehr einfaches Validierungsrückruf\-Szenario, das Validieren einer Eigenschaft, die typisiert wird, wenn das <xref:System.Double>\-Primitiv nicht <xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity> ist.  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>   
## Rückrufe zum Umwandeln von Werten und durch geänderte Eigenschaften ausgelöste Ereignisse  
 Rückrufe zum Umwandeln von Werten übergeben die spezifische <xref:System.Windows.DependencyObject>\-Instanz für Eigenschaften, ebenso wie <xref:System.Windows.PropertyChangedCallback>\-Implementierungen dies tun, die durch das Eigenschaftensystem aufgerufen werden, wenn der Wert einer Abhängigkeitseigenschaft geändert wird.  Wenn Sie diese zwei Rückrufe in Verbindung miteinander verwenden, können Sie eine Reihe von Eigenschaften für Elemente erstellen, bei denen Änderungen einer Eigenschaft eine Koersion oder Neuauswertung einer anderen Eigenschaft erzwingt.  
  
 Ein typisches Szenario für die Verwendung einer Verknüpfung von Abhängigkeitseigenschaften wäre eine durch die Benutzeroberfläche gesteuerte Eigenschaft, bei der das Element eine Eigenschaft jeweils für den Minimal\- und den Maximalwert und eine dritte Eigenschaft für den tatsächlichen oder aktuellen Wert enthält.  Wenn in diesem Fall der Maximalwert so eingestellt wird, dass der aktuelle Wert den neuen Maximalwert übersteigt, sollte der aktuelle Wert so umgewandelt werden, dass er den neuen Maximalwert nicht übersteigt. Eine vergleichbare Beziehung muss zwischen dem Minimalwert und dem aktuellen Wert hergestellt werden.  
  
 Nachfolgend ein sehr kurzer Beispielcode für nur eine der drei Abhängigkeitseigenschaften, um diese Beziehung zu veranschaulichen.  Das Beispiel zeigt, wie die `CurrentReading`\-Eigenschaft eines "Min\/Max\/Aktuell"\-Satzes von miteinander verbundenen \*Reading\-Eigenschaften registriert ist.  Dabei wird die Validierung verwendet, die im vorherigen Abschnitt erläutert wurde.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Der durch die geänderte Eigenschaft ausgelöste Rückruf für den aktuellen Wert wird verwendet, um die Änderung an andere Abhängigkeitseigenschaften weiterzuleiten, indem die Rückrufe zum Umwandeln von Werten explizit aufgerufen werden, die für diese anderen Eigenschaften registriert sind.  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 Der Rückruf zum Umwandeln von Werten prüft die Werte der Eigenschaften, von denen die aktuelle Eigenschaft potenziell abhängig ist, und wandelt den aktuellen Wert um, falls erforderlich:  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
>  Standardwerte von Eigenschaften werden nicht umgewandelt.  Ein Eigenschaftswert, der gleich dem Standardwert ist, kann vorkommen, wenn ein Eigenschaftswert immer noch seine anfängliche Standardeinstellung hat oder wenn andere Werte durch <xref:System.Windows.DependencyObject.ClearValue%2A> gelöscht werden.  
  
 Die Rückrufe zum Umwandeln von Werten und die durch geänderte Eigenschaften ausgelösten Rückrufe sind Teil der Eigenschaftenmetadaten.  Daher können Sie die Rückrufe für eine bestimmte Abhängigkeitseigenschaft ändern, wie sie für einen Typ vorhanden ist, den Sie von dem Typ ableiten, dem die Abhängigkeitseigenschaft gehört, indem Sie die Metadaten für diese Eigenschaft für Ihren Typ überschreiben.  
  
<a name="Advanced"></a>   
## Erweiterte Umwandlung und Rückrufszenarien  
  
### Einschränkungen und gewünschte Werte  
 Die <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>\-Rückrufe werden durch das Eigenschaftensystem verwendet, um einen Wert gemäß der von Ihnen deklarierten Logik umzuwandeln. Ein umgewandelter Wert einer lokal festgelegten Eigenschaft bleibt jedoch weiterhin intern ein "gewünschter Wert".  Wenn die Einschränkungen auf anderen Eigenschaftswerten basieren, die sich dynamisch während der Lebensdauer einer Anwendung ändern können, dann werden auch die Umwandlungseinschränkungen dynamisch geändert, und die eingeschränkte Eigenschaft kann ihren Wert ändern, um dem gewünschten Wert unter Berücksichtigung der neuen Einschränkungen möglichst nah zu kommen.  Der Wert nimmt den gewünschten Wert an, wenn alle Einschränkungen aufgehoben werden.  Sie können möglicherweise recht komplizierte Abhängigkeitsszenarien einführen, wenn Sie über mehrere Eigenschaften verfügen, die zirkulär voneinander abhängig sind.  Im Szenario "Min\/Max\/Aktuell" könnten Sie beispielsweise festlegen, dass der Benutzer den Mindest\- und den Höchstwert festlegen kann.  Wenn das der Fall ist, müssten Sie als Umwandlung festlegen, dass der Maximalwert immer größer ist als der Minimalwert und umgekehrt.  Wenn diese Koersion jedoch aktiv ist und der Maximalwert bei der Umwandlung auf den Minimalwert gesetzt wird, nimmt der aktuelle Wert einen nicht festlegbaren Zustand an, da er von dem Minimal\- und Maximalwert abhängig ist und auf den Bereich zwischen diesen beiden Werten eingeschränkt ist, der dann gleich null ist.  Wenn anschließend der Maximal\- oder der Minimalwert angepasst wird, scheint der aktuelle Wert einem dieser Wert zu "folgen", da der gewünschte aktuelle Wert weiterhin gespeichert ist und bei der Lockerung der Einschränkungen der Versuch unternommen wird, den gewünschten Wert zu erreichen.  
  
 Technisch gesehen stellen komplexe Abhängigkeiten kein Problem dar, aber sie können die Leistung beeinträchtigen, wenn sie eine große Anzahl von Neuauswertungen erforderlich machen. Außerdem können sie den Benutzer verwirren, wenn sie sich direkt auf die Benutzeroberfläche auswirken.  Sie müssen daher sehr sorgfältig mit durch geänderte Eigenschaften ausgelösten Rückrufen und Rückrufen zum Umwandeln von Werten umgehen, um sicherzustellen, dass die versuchte Umwandlung so eindeutig wie möglich behandelt werden kann und keine zu starke Einschränkung herstellt.  
  
### Verwenden von CoerceValue zum Verwerfen von Wertänderungen  
 Das Eigenschaftensystem behandelt jeden <xref:System.Windows.CoerceValueCallback>, der den Wert <xref:System.Windows.DependencyProperty.UnsetValue> zurückgibt, als besonderen Fall.  Dieser besondere Fall bedeutet, dass die Eigenschaftenänderung, die zu dem aufgerufenen <xref:System.Windows.CoerceValueCallback> führt, durch das Eigenschaftensystem zurückgewiesen werden sollte und das Eigenschaftensystem stattdessen den vorherigen Wert der Eigenschaft melden sollte.  Dieser Mechanismus kann nützlich sein, um zu überprüfen, ob asynchron initiierte Änderungen einer Eigenschaft weiterhin gültig für den aktuellen Objektzustand sind, und die Änderungen zu unterdrücken, falls das nicht der Fall ist.  Ein weiteres mögliches Szenario sieht so aus, dass Sie selektiv einen Wert abhängig davon unterdrücken können, welche Komponente der Eigenschaftswertbestimmung verantwortlich für den gemeldeten Wert ist.  Dazu können Sie die im Rückruf übergebene <xref:System.Windows.DependencyProperty> mit dem Eigenschaftenbezeichner als Eingabe für die <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A> verwenden und anschließend die <xref:System.Windows.ValueSource> verarbeiten.  
  
## Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)