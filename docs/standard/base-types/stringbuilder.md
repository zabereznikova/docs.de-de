---
title: Verwenden der StringBuilder-Klasse in .NET
description: Hier erfahren Sie mehr über das Verwenden der StringBuilder-Klasse in .NET. Verwenden Sie diese Klasse, um eine Zeichenfolge zu ändern, ohne dabei ein neues Objekt zu erstellen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
ms.openlocfilehash: 83d4b9327b55c511e2a46486e519e3cd0c77b1a3
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803226"
---
# <a name="using-the-stringbuilder-class-in-net"></a>Verwenden der StringBuilder-Klasse in .NET
Das <xref:System.String>-Objekt ist unveränderlich. Jedes Mal, wenn Sie eine der Methoden in der <xref:System.String?displayProperty=nameWithType>-Klasse verwenden, erstellen Sie ein neues Zeichenfolgenobjekt im Speicher, das eine neue Speicherbelegung für dieses neue Objekt erfordert. In Fällen, in denen Sie wiederholte Änderungen an einer Zeichenfolge vornehmen müssen, kann der Mehraufwand, der mit dem Erstellen eines neuen <xref:System.String>-Objekts verbunden ist, erheblich sein. Die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse kann verwendet werden, wenn Sie eine Zeichenfolge ändern möchten, ohne ein neues Objekt zu erstellen. Beispielsweise lässt sich durch Verwenden der <xref:System.Text.StringBuilder>-Klasse die Leistung steigern, wenn zahlreiche Zeichenfolgen in einer Schleife verkettet werden.  
  
## <a name="importing-the-systemtext-namespace"></a>Importieren des System.Text-Namespace  
 Die <xref:System.Text.StringBuilder>-Klasse befindet sich im <xref:System.Text>-Namespace.  Wenn Sie in Ihrem Code nicht den vollqualifizierten Typnamen bereitstellen möchten, können Sie den <xref:System.Text>-Namespace importieren:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Instanziieren eines StringBuilder-Objekts  
 Sie können eine neue Instanz der <xref:System.Text.StringBuilder>-Klasse erstellen, indem Sie Ihre Variable mit einer der Methoden für überladene Konstruktoren initialisieren, wie im folgenden Beispiel verdeutlicht.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Festlegen von Kapazität und Länge  
 Obwohl ein <xref:System.Text.StringBuilder>-Objekt ein dynamisches Objekt ist, das die Erhöhung der Zeichenanzahl der darin gekapselten Zeichenfolge ermöglicht, können Sie einen Wert für die maximale Anzahl von Zeichen festlegen, die das Objekt enthalten darf. Dieser Wert wird als Kapazität des Objekts bezeichnet und darf nicht mit der Länge der Zeichenfolge verwechselt werden, die im aktuellen <xref:System.Text.StringBuilder>-Objekt enthalten ist. Sie könnten z.B. eine neue Instanz der <xref:System.Text.StringBuilder>-Klasse mit der Zeichenfolge „Hello“ erstellen, die eine Länge von 5 Zeichen hat, und angeben, dass das Objekt eine maximale Kapazität von 25 Zeichen hat. Bei einer Änderung des <xref:System.Text.StringBuilder>-Objekts ordnet es sich selbst erst dann eine neue Größe zu, wenn die Kapazität erreicht ist. Tritt dieser Fall ein, wird der neue Speicherplatz automatisch zugeordnet, und die Kapazität wird verdoppelt. Sie können die Kapazität der <xref:System.Text.StringBuilder>-Klasse angeben, indem Sie einen der überladenen Konstruktoren verwenden. Im folgenden Beispiel wird festgelegt, dass das `myStringBuilder`-Objekt auf maximal 25 Zeichen erweitert werden kann.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Darüber hinaus können Sie die <xref:System.Text.StringBuilder.Capacity%2A>-Eigenschaft mit Lese-/Schreibzugriff verwenden, um die maximale Länge Ihres Objekts festzulegen. Im folgenden Beispiel wird die **Capacity**-Eigenschaft verwendet, um die maximale Objektlänge zu definieren.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Mithilfe der <xref:System.Text.StringBuilder.EnsureCapacity%2A>-Methode kann die Kapazität des aktuellen **StringBuilder**-Objekts überprüft werden. Ist die Kapazität größer als der übergebene Wert, wird keine Änderung vorgenommen. Ist die Kapazität dagegen kleiner als der übergebene Wert, wird die aktuelle Kapazität entsprechend dem übergebenen Wert geändert.  
  
 Die <xref:System.Text.StringBuilder.Length%2A>-Eigenschaft kann auch angezeigt oder festgelegt werden. Wenn Sie für die **Length**-Eigenschaft einen Wert festlegen, der größer ist als der Wert der **Capacity**-Eigenschaft, wird die **Capacity**-Eigenschaft automatisch auf den Wert der **Length**-Eigenschaft festgelegt. Ist die **Length**-Eigenschaft auf einen Wert festgelegt, der kleiner als die Länge der Zeichenfolge im aktuellen **StringBuilder**-Objekt ist, wird die Zeichenfolge gekürzt.  
  
## <a name="modifying-the-stringbuilder-string"></a>Ändern der StringBuilder-Zeichenfolge  
 In der folgenden Tabelle sind die Methoden aufgeführt, mit denen Sie den Inhalt eines **StringBuilder**-Objekts ändern können.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Fügt Informationen an das Ende des aktuellen **StringBuilder**-Objekts an.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Ersetzt einen in einer Zeichenfolge übergebenen Formatbezeichner durch formatierten Text.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Fügt eine Zeichenfolge oder ein Objekt in den angegebenen Index des aktuellen **StringBuilder**-Objekts ein.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Entfernt eine angegebene Anzahl von Zeichen aus dem aktuellen **StringBuilder**-Objekt.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Hiermit werden alle Vorkommen eines angegebenen Zeichens bzw. einer angegebenen Zeichenfolge im aktuellen **StringBuilder**-Objekt durch ein anderes Zeichen bzw. eine andere Zeichenfolge ersetzt.|  
  
### <a name="append"></a>Append  
 Mithilfe der **Append**-Methode kann Text oder eine Zeichenfolgendarstellung eines Objekts am Ende einer Zeichenfolge hinzugefügt werden, die durch den aktuellen **StringBuilder** dargestellt wird. Im folgenden Beispiel wird ein **StringBuilder**-Objekt auf „Hello World“ initialisiert und anschließend Text am Ende des Objekts angefügt. Speicherplatz wird automatisch nach Bedarf zugeordnet.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 Die <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>-Methode fügt Text am Ende des <xref:System.Text.StringBuilder>-Objekts hinzu. Die Methode unterstützt das Feature für die kombinierte Formatierung (weitere Informationen finden Sie unter [Kombinierte Formatierung](composite-formatting.md)) durch Aufrufen der <xref:System.IFormattable>-Implementierung der Objekte, die formatiert werden sollen. Daher akzeptiert sie die Standardformatzeichenfolgen für numerische Werte, Datums- und Uhrzeitwerte sowie Enumerationswerte, die benutzerdefinierten Formatzeichenfolgen für numerische Werte sowie Datums- und Uhrzeitwerte und die Formatzeichenfolgen, die für benutzerdefinierte Typen definiert sind. (Weitere Informationen zur Formatierung finden Sie unter [Formatieren von Typen](formatting-types.md).) Sie können diese Methode verwenden, um das Format von Variablen anzupassen und diese Werte an ein <xref:System.Text.StringBuilder>-Objekt anzufügen. Im folgenden Beispiel wird die <xref:System.Text.StringBuilder.AppendFormat%2A>-Methode verwendet, um einen als Währungswert formatierten ganzzahligen Wert am Ende eines <xref:System.Text.StringBuilder>-Objekts einzufügen.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 Mit der <xref:System.Text.StringBuilder.Insert%2A>-Methode wird an einer angegebenen Position im aktuellen <xref:System.Text.StringBuilder>-Objekt eine Zeichenfolge oder ein Objekt hinzugefügt. Im folgenden Beispiel wird mit dieser Methode ein Wort an der sechsten Position eines <xref:System.Text.StringBuilder>-Objekts eingefügt.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Remove  
 Über die **Remove**-Methode können Sie, beginnend bei einem angegebenen nullbasierten Index, eine bestimmte Anzahl von Zeichen aus dem aktuellen <xref:System.Text.StringBuilder>-Objekt entfernen. Im folgenden Beispiel wird die **Remove**-Methode verwendet, um ein <xref:System.Text.StringBuilder>-Objekt zu kürzen.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Replace  
 Mithilfe der **Replace**-Methode können Zeichen im <xref:System.Text.StringBuilder>-Objekt durch ein anderes angegebenes Zeichen ersetzt werden. Im folgenden Beispiel wird die **Replace**-Methode verwendet, um in einem <xref:System.Text.StringBuilder>-Objekt nach allen Vorkommen des Ausrufezeichens (!) zu suchen und diese durch das Fragezeichen (?) zu ersetzen.  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Konvertieren eines StringBuilder-Objekts in eine Zeichenfolge  
 Sie müssen das <xref:System.Text.StringBuilder>-Objekt in ein <xref:System.String>-Objekt konvertieren, bevor Sie die vom <xref:System.Text.StringBuilder>-Objekt dargestellte Zeichenfolge an eine Methode mit einem <xref:System.String>-Parameter übergeben können oder diese auf der Benutzeroberfläche anzeigen. Diese Konvertierung führen Sie aus, indem Sie die <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>-Methode aufrufen. Im folgenden Beispiel werden einige <xref:System.Text.StringBuilder>-Methoden und anschließend die <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType>-Methode aufgerufen, um die Zeichenfolge anzuzeigen.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- [Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)
- [Formatierung von Typen](formatting-types.md)
