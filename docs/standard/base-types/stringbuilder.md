---
title: "Verwenden der StringBuilder-Klasse in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Remove-Methode"
  - "Zeichenfolgen [.NET Framework], Kapazitäten"
  - "StringBuilder-Objekt"
  - "Replace-Methode"
  - "AppendFormat-Methode"
  - "Append-Methode"
  - "Insert-Methode"
  - "Zeichenfolgen [.NET Framework], StringBuilder-Objekt"
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Verwenden der StringBuilder-Klasse in .NET Framework
Das <xref:System.String>\-Objekt ist unveränderlich. Jedes Mal, wenn Sie eine der Methoden in der <xref:System.String?displayProperty=fullName>\-Klasse verwenden, erstellen Sie ein neues Zeichenfolgenobjekt im Arbeitsspeicher, das eine neue Zuordnung von Speicherplatz für dieses neue Objekt erfordert. In Fällen, in denen Sie wiederholte Änderungen an einer Zeichenfolge vornehmen müssen, kann der Aufwand, der mit dem Erstellen eines neuen <xref:System.String>\-Objekts verbunden ist, erheblich sein. Die <xref:System.Text.StringBuilder?displayProperty=fullName>\-Klasse kann verwendet werden, wenn Sie eine Zeichenfolge ändern möchten, ohne ein neues Objekt zu erstellen. Beispielsweise lässt sich durch Verwenden der <xref:System.Text.StringBuilder>\-Klasse die Leistung steigern, wenn zahlreiche Zeichenfolgen in einer Schleife verkettet werden.  
  
## Importieren des System.Type\-Namespace  
 Die <xref:System.Text.StringBuilder>\-Klasse befindet sich im <xref:System.Text>\-Namespace.  Wenn Sie in Ihrem Code nicht den vollqualifizierten Typnamen bereitstellen möchten, können Sie den <xref:System.Text>\-Namespace importieren:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## Instanziieren eines StringBuilder\-Objekts  
 Sie können eine neue Instanz der <xref:System.Text.StringBuilder>\-Klasse erstellen, indem Sie Ihre Variable mit einer der Methoden für überladene Konstruktoren initialisieren, wie im folgenden Beispiel verdeutlicht.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## Festlegen von Kapazität und Länge  
 Obwohl ein <xref:System.Text.StringBuilder>\-Objekt ein dynamisches Objekt ist, das es Ihnen ermöglicht, die Anzahl der Zeichen in der darin gekapselten Zeichenfolge zu erhöhen, können Sie einen Wert für die maximale Anzahl von Zeichen festlegen, die das Objekt enthalten darf. Dieser Wert wird als die Kapazität des Objekts bezeichnet und darf nicht mit der Länge der Zeichenfolge verwechselt werden, die im aktuellen <xref:System.Text.StringBuilder>\-Objekt enthalten ist. Sie könnten z. B. eine neue Instanz der <xref:System.Text.StringBuilder>\-Klasse mit der Zeichenfolge „Hello“ erstellen, die eine Länge von 5 Zeichen hat, und Sie könnten angeben, dass das Objekt eine maximale Kapazität von 25 Zeichen hat. Wenn das <xref:System.Text.StringBuilder>\-Objekt geändert wird, ordnet es für sich selbst keine neue Größe zu, bis die Kapazität erreicht ist. Tritt dieser Fall ein, wird der neue Speicherplatz automatisch zugeordnet, und die Kapazität wird verdoppelt. Sie können die Kapazität der <xref:System.Text.StringBuilder>\-Klasse angeben, indem Sie einen der überladenen Konstruktoren verwenden. Im folgenden Beispiel wird festgelegt, dass das `MyStringBuilder`\-Objekt auf maximal 25 Zeichen erweitert werden kann.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Darüber hinaus können Sie die <xref:System.Text.StringBuilder.Capacity%2A>\-Eigenschaft mit Schreib\-\/Lesezugriff verwenden, um die maximale Länge Ihres Objekts festzulegen. Im folgenden Beispiel wird die **Capacity**\-Eigenschaft verwendet, um die maximale Objektlänge zu definieren.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Mithilfe der <xref:System.Text.StringBuilder.EnsureCapacity%2A>\-Methode kann die Kapazität des aktuellen **StringBuilder**\-Objekts überprüft werden. Ist die Kapazität größer als der übergebene Wert, wird keine Änderung vorgenommen. Ist die Kapazität dagegen kleiner als der übergebene Wert, wird die aktuelle Kapazität entsprechend dem übergebenen Wert geändert.  
  
 Die <xref:System.Text.StringBuilder.Length%2A>\-Eigenschaft kann auch angezeigt oder festgelegt werden. Wenn Sie für die **Length**\-Eigenschaft einen Wert festlegen, der größer ist als der Wert der **Capacity**\-Eigenschaft, wird die **Capacity**\-Eigenschaft automatisch auf den Wert der **Length**\-Eigenschaft festgelegt. Ist die **Length**\-Eigenschaft auf einen Wert festgelegt, der kleiner als die Länge der Zeichenfolge im aktuellen **StringBuilder**\-Objekt ist, wird die Zeichenfolge gekürzt.  
  
## Ändern der StringBuilder\-Zeichenfolge  
 In der folgenden Tabelle sind die Methoden aufgeführt, mit denen Sie den Inhalt eines **StringBuilder**\-Objekts ändern können.  
  
|Methodenname|Verwendung|  
|------------------|----------------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>|Fügt Informationen an das Ende des aktuellen **StringBuilder**\-Objekts an.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName>|Ersetzt einen in einer Zeichenfolge übergebenen Formatbezeichner durch formatierten Text.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=fullName>|Fügt eine Zeichenfolge oder ein Objekt in den angegebenen Index des aktuellen **StringBuilder**\-Objekts ein.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=fullName>|Entfernt die jeweils angegebene Anzahl von Zeichen aus dem aktuellen **StringBuilder**\-Objekt.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=fullName>|Ersetzt ein angegebenes Zeichen an einem angegebenen Index.|  
  
### Anfügen  
 Mithilfe der **Append**\-Methode kann Text oder eine Zeichenfolgendarstellung eines Objekts am Ende einer Zeichenfolge hinzugefügt werden, die durch den aktuellen **StringBuilder** dargestellt wird. Im folgenden Beispiel wird ein **StringBuilder**\-Objekt auf „Hello World“ initialisiert und anschließend Text am Ende des Objekts angefügt. Speicherplatz wird automatisch nach Bedarf zugeordnet.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### AppendFormat  
 Die <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName>\-Methode fügt Text am Ende des <xref:System.Text.StringBuilder>\-Objekts hinzu. Die Methode unterstützt die Funktion für die kombinierte Formatierung \(weitere Informationen finden Sie unter [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)\) durch Aufrufen der <xref:System.IFormattable>\-Implementierung der Objekte, die formatiert werden sollen. Daher akzeptiert sie die Standardformatzeichenfolgen für numerische Werte, Datums\- und Uhrzeitwerte sowie Enumerationswerte, die benutzerdefinierten Formatzeichenfolgen für numerische Werte sowie Datums\- und Uhrzeitwerte und die Formatzeichenfolgen, die für benutzerdefinierte Typen definiert sind. \(Weitere Informationen zur Formatierung finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md).\) Sie können diese Methode verwenden, um das Format von Variablen anzupassen und diese Werte an <xref:System.Text.StringBuilder>\-Objekt anzufügen. Im folgenden Beispiel wird die <xref:System.Text.StringBuilder.AppendFormat%2A>\-Methode verwendet, um einen als Währungsbetrag formatierten ganzzahligen Wert am Ende eines <xref:System.Text.StringBuilder>\-Objekts einzufügen.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### Insert  
 Mit der <xref:System.Text.StringBuilder.Insert%2A>\-Methode wird an einer angegebenen Position im aktuellen <xref:System.Text.StringBuilder>\-Objekt eine Zeichenfolge oder ein Objekt hinzugefügt. Im folgenden Beispiel wird mit dieser Methode ein Wort an der sechsten Position eines <xref:System.Text.StringBuilder>\-Objekts eingefügt.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### Remove  
 Über die **Remove**\-Methode können Sie, beginnend bei einem angegebenen nullbasierten Index, eine bestimmte Anzahl von Zeichen aus dem aktuellen <xref:System.Text.StringBuilder>\-Objekt entfernen. Im folgenden Beispiel wird die **Remove**\-Methode verwendet, um ein <xref:System.Text.StringBuilder>\-Objekt zu kürzen.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### Replace  
 Mithilfe der **Replace**\-Methode können Zeichen im <xref:System.Text.StringBuilder>\-Objekt durch ein anderes angegebenes Zeichen ersetzt werden. Im folgenden Beispiel wird die **Replace**\-Methode verwendet, um in einem <xref:System.Text.StringBuilder>\-Objekt nach allen Vorkommen des Ausrufezeichens \(\!\) zu suchen und diese durch das Fragezeichen \(?\) zu ersetzen.  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## Konvertieren eines StringBuilder\-Objekts in eine Zeichenfolge  
 Sie müssen das <xref:System.Text.StringBuilder>\-Objekt in ein <xref:System.String>\-Objekt konvertieren, bevor Sie die vom <xref:System.Text.StringBuilder>\-Objekt dargestellte Zeichenfolge an eine Methode übergeben können, die einen <xref:System.String>\-Parameter hat, oder bevor Sie sie in der Benutzeroberfläche anzeigen. Diese Konvertierung führen Sie aus, indem Sie die <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName>\-Methode aufrufen. Im folgenden Beispiel werden einige <xref:System.Text.StringBuilder>\-Methoden aufgerufen, und anschließend wird die <xref:System.Text.StringBuilder.ToString?displayProperty=fullName>\-Methode aufgerufen, um die Zeichenfolge anzuzeigen.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## Siehe auch  
 <xref:System.Text.StringBuilder?displayProperty=fullName>   
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)   
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)