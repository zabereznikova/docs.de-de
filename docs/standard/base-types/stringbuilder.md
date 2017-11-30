---
title: Verwenden der StringBuilder-Klasse in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>Verwenden der StringBuilder-Klasse in .NET
Die <xref:System.String> -Objekt unveränderlich ist. Jedes Mal, wenn Sie eine der Methoden in der <xref:System.String?displayProperty=nameWithType> -Klasse, erstellen Sie ein neues Zeichenfolgenobjekt im Arbeitsspeicher, das eine neue Zuordnung von Speicherplatz für das neue Objekt erfordert. In Situationen, in denen Sie wiederholte Änderungen an einer Zeichenfolge durchführen müssen, der Aufwand beim Erstellen eines neuen zugeordneten <xref:System.String> Objekt kann recht kostenaufwendig sein. Die <xref:System.Text.StringBuilder?displayProperty=nameWithType> -Klasse kann verwendet werden, wenn Sie eine Zeichenfolge zu ändern, ohne ein neues Objekt erstellen möchten. Beispiel für die Verwendung der <xref:System.Text.StringBuilder> Klasse Leistung steigern, wenn zahlreiche Zeichenfolgen in einer Schleife verkettet.  
  
## <a name="importing-the-systemtext-namespace"></a>Importieren des System.Text-Namespace  
 Die <xref:System.Text.StringBuilder> Klasse befindet sich der <xref:System.Text> Namespace.  Um zu vermeiden, einen voll qualifizierten Typnamen im Code angeben zu müssen, können Sie importieren die <xref:System.Text> Namespace:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Instanziieren eines StringBuilder-Objekts  
 Sie können eine neue Instanz der erstellen die <xref:System.Text.StringBuilder> Klasse, indem Sie die Variable mit einer der Methoden für überladene Konstruktoren initialisieren, wie im folgenden Beispiel dargestellt.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Festlegen von Kapazität und Länge  
 Obwohl die <xref:System.Text.StringBuilder> ist ein dynamisches Objekt, mit dem Sie die Anzahl der Zeichen in der Zeichenfolge zu erweitern, die diese kapselt, können Sie angeben, einen Wert für die maximale Anzahl von Zeichen, die sie aufnehmen kann. Dieser Wert wird als die Kapazität des Objekts bezeichnet und darf nicht mit der Länge der Zeichenfolge verwechselt werden, die das aktuelle <xref:System.Text.StringBuilder> enthält. Beispielsweise können Sie eine neue Instanz der erstellen die <xref:System.Text.StringBuilder> -Klasse mit der Zeichenfolge "Hello", die eine Länge von 5, und Sie kann festlegen, dass das Objekt eine maximale Kapazität von 25 hat. Beim Ändern der <xref:System.Text.StringBuilder>, es ist nicht für sich selbst neu Größe zuzuordnen, bis die Kapazität erreicht ist. Tritt dieser Fall ein, wird der neue Speicherplatz automatisch zugeordnet, und die Kapazität wird verdoppelt. Sie können die Kapazität der angeben der <xref:System.Text.StringBuilder> -Klasse unter Verwendung einer der überladenen Konstruktoren. Im folgenden Beispiel wird festgelegt, dass das `MyStringBuilder`-Objekt auf maximal 25 Zeichen erweitert werden kann.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Darüber hinaus können Sie den Lese-/Schreibzugriff <xref:System.Text.StringBuilder.Capacity%2A> Eigenschaft, um die maximale Länge Ihres Objekts festzulegen. Im folgenden Beispiel wird die **Capacity**-Eigenschaft verwendet, um die maximale Objektlänge zu definieren.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Die <xref:System.Text.StringBuilder.EnsureCapacity%2A> Methode kann verwendet werden, um die Kapazität des aktuellen überprüft **StringBuilder**. Ist die Kapazität größer als der übergebene Wert, wird keine Änderung vorgenommen. Ist die Kapazität dagegen kleiner als der übergebene Wert, wird die aktuelle Kapazität entsprechend dem übergebenen Wert geändert.  
  
 Die <xref:System.Text.StringBuilder.Length%2A> Eigenschaft kann auch angezeigt oder festgelegt werden. Wenn Sie für die **Length**-Eigenschaft einen Wert festlegen, der größer ist als der Wert der **Capacity**-Eigenschaft, wird die **Capacity**-Eigenschaft automatisch auf den Wert der **Length**-Eigenschaft festgelegt. Ist die **Length**-Eigenschaft auf einen Wert festgelegt, der kleiner als die Länge der Zeichenfolge im aktuellen **StringBuilder**-Objekt ist, wird die Zeichenfolge gekürzt.  
  
## <a name="modifying-the-stringbuilder-string"></a>Ändern der StringBuilder-Zeichenfolge  
 In der folgenden Tabelle sind die Methoden aufgeführt, mit denen Sie den Inhalt eines **StringBuilder**-Objekts ändern können.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Fügt Informationen an das Ende des aktuellen **StringBuilder**-Objekts an.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Ersetzt einen in einer Zeichenfolge übergebenen Formatbezeichner durch formatierten Text.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Fügt eine Zeichenfolge oder ein Objekt in den angegebenen Index des aktuellen **StringBuilder**-Objekts ein.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Entfernt eine angegebene Anzahl von Zeichen aus dem aktuellen **StringBuilder**-Objekt.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Ersetzt ein angegebenes Zeichen an einem angegebenen Index.|  
  
### <a name="append"></a>Anfügen  
 Die **Append** Methode kann verwendet werden, um Text oder eine Zeichenfolgendarstellung eines Objekts an das Ende einer Zeichenfolge, die vom aktuellen hinzufügen **StringBuilder**. Im folgenden Beispiel wird ein **StringBuilder**-Objekt auf „Hello World“ initialisiert und anschließend Text am Ende des Objekts angefügt. Speicherplatz wird automatisch nach Bedarf zugeordnet.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 Die <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> Methode fügt Text an das Ende der <xref:System.Text.StringBuilder> Objekt. Es unterstützt die Funktion für kombinierte Formatierung (Weitere Informationen finden Sie unter [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)) durch Aufrufen der <xref:System.IFormattable> Implementierung des Objekts oder der Objekte, die formatiert werden. Daher akzeptiert sie die Standardformatzeichenfolgen für numerische Werte, Datums- und Uhrzeitwerte sowie Enumerationswerte, die benutzerdefinierten Formatzeichenfolgen für numerische Werte sowie Datums- und Uhrzeitwerte und die Formatzeichenfolgen, die für benutzerdefinierte Typen definiert sind. (Weitere Informationen zur Formatierung finden Sie unter [Formatieren von Typen](../../../docs/standard/base-types/formatting-types.md).) Sie können diese Methode verwenden, um das Format von Variablen anzupassen, und fügen diese Werte in einer <xref:System.Text.StringBuilder>. Im folgenden Beispiel wird die <xref:System.Text.StringBuilder.AppendFormat%2A> Methode, um einen ganzzahligen Wert platzieren formatiert als Währungswert am Ende einer <xref:System.Text.StringBuilder> Objekt.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 Die <xref:System.Text.StringBuilder.Insert%2A> Methode fügt eine Zeichenfolge oder ein Objekt an eine angegebene Position in der aktuellen <xref:System.Text.StringBuilder> Objekt. Im folgenden Beispiel wird diese Methode, um ein Wort in der sechsten Position einzufügen ein <xref:System.Text.StringBuilder> Objekt.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Remove  
 Sie können die **entfernen** Methode, um eine angegebene Anzahl von Zeichen aus dem aktuellen entfernen <xref:System.Text.StringBuilder> Objekt, beginnend am angegebenen nullbasierten Index. Im folgenden Beispiel wird die **entfernen** Methode zum Kürzen einer <xref:System.Text.StringBuilder> Objekt.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Ersetzen  
 Die **ersetzen** Methode kann verwendet werden, um die Zeichen innerhalb der <xref:System.Text.StringBuilder> angegebene Objekt mit einem anderen Zeichen. Im folgenden Beispiel wird die **ersetzen** Methode zum Suchen einer <xref:System.Text.StringBuilder> -Objekt alle Instanzen des Ausrufezeichens (!) und Fragezeichen (?) ersetzt.  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Konvertieren eines StringBuilder-Objekts in eine Zeichenfolge  
 Müssen konvertiert die <xref:System.Text.StringBuilder> -Objekt an eine <xref:System.String> -Objekt, bevor Sie die Zeichenfolge dargestellte übergeben können die <xref:System.Text.StringBuilder> Objekt, das eine Methode mit einer <xref:System.String> Parameter oder in der Benutzeroberfläche anzeigen. Sie führen diese Konvertierung durch Aufrufen der <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> Methode. Im folgenden Beispiel wird eine Anzahl von <xref:System.Text.StringBuilder> Methoden und ruft dann die <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> Methode zur Anzeige der Zeichenfolge.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
