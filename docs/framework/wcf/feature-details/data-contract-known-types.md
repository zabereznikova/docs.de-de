---
title: Bekannte Typen in Datenverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
ms.openlocfilehash: b7d78def4d656dea59af5400c7ed7deeef28cd0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597448"
---
# <a name="data-contract-known-types"></a>Bekannte Typen in Datenverträgen
Die <xref:System.Runtime.Serialization.KnownTypeAttribute> -Klasse ermöglicht es Ihnen, vorab die Typen anzugeben, die während der Deserialisierung in Betracht gezogen werden sollen. Ein Arbeitsbeispiel finden Sie unter [Known Types](../samples/known-types.md) .  
  
 Beim Übergeben von Parametern und Rückgabewerten zwischen einem Client und einem Dienst verwenden normalerweise beide Endpunkte sämtliche Datenverträge für die zu übertragenden Daten gemeinsam. Unter den folgenden Umständen ist dies allerdings nicht der Fall:  
  
- Der gesendete Datenvertrag wird vom erwarteten Datenvertrag abgeleitet. Weitere Informationen finden Sie im Abschnitt zur Vererbung in der [Daten Vertrags Äquivalenz](data-contract-equivalence.md). In diesem Fall gilt für die übertragenen Daten nicht der Datenvertrag, der vom empfangenden Endpunkt erwartet wird.  
  
- Die zu übertragenden Informationen werden als zu einem Schnittstellentyp zugehörig deklariert, nicht als Klasse, Struktur oder Enumeration. Daher kann nicht im Vorhinein bekannt sein, welcher die Schnittstelle implementierende Typ tatsächlich gesendet wird, und folglich kann der empfangende Endpunkt nicht vorab den Datenvertrag für die übermittelten Daten bestimmen.  
  
- Für die zu sendenden Informationen wird der Typ <xref:System.Object>deklariert. Weil jeder Typ von <xref:System.Object>erbt und nicht im Vorhinein bekannt sein kann, welcher die Schnittstelle implementierender Typ tatsächlich gesendet wird, und kann der empfangende Endpunkt nicht vorab den Datenvertrag für die übermittelten Daten bestimmen. Dies ist ein Sonderfall des ersten Punkts: Jeder Datenvertrag ist vom Standardvertrag abgeleitet, d.&#160;h. einem leeren Vertrag, der für <xref:System.Object>generiert wird.  
  
- Einige Typen, die .NET Framework Typen enthalten, haben Member, die sich in einer der drei vorangegangenen Kategorien befinden. Zum Beispiel verwendet <xref:System.Collections.Hashtable> den Typ <xref:System.Object> , um die tatsächlichen Objekte in der Hashtabelle zu speichern. Beim Serialisieren dieser Typen kann die Empfängerseite nicht im Voraus den Datenvertrag für diese Member bestimmen.  
  
## <a name="the-knowntypeattribute-class"></a>Die KnownTypeAttribute-Klasse  
 Wenn Daten an einem empfangenden Endpunkt ankommen, versucht die WCF-Laufzeit, die Daten in eine Instanz eines Common Language Runtime (CLR)-Typs zu deserialisieren. Zur Auswahl des Typs, der für die Deserialisierung instanziiert wird, wird zuerst die eingehende Nachricht überprüft, um den Datenvertrag zu ermitteln, dem der Inhalt der Nachricht entspricht. Die Deserialisierungs-Engine versucht dann, den CLR-Typ zu finden, der einen mit dem Nachrichteninhalt kompatiblen Datenvertrag implementiert. Die Gruppe potenzieller Typen, die die Deserialisierungs-Engine während dieses Prozesses zulässt, wird als die Gruppe "bekannter Typen" des Deserialisierers bezeichnet.  
  
 Eine Methode, die Deserialisierungs-Engine über einen Typ zu informieren, besteht im Einsatz von <xref:System.Runtime.Serialization.KnownTypeAttribute>. Das Attribut kann nicht auf einzelne Datenmember, sondern nur auf gesamte Datenvertragstypen angewendet werden. Das Attribut wird auf einen *äußeren Typ* angewendet, der eine Klasse oder eine Struktur sein kann. Grundsätzlich wird durch die Anwendung des Attributs ein Typ als "bekannter Typ" angegeben. Dadurch wird der bekannte Typ Bestandteil der Gruppe bekannter Typen, wenn ein Objekt des äußeren Typs oder ein Objekt, auf das durch ein Member des äußeren Typs verwiesen wird, deserialisiert wird. Auf einen Typ können mehrere <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attribute angewendet werden.  
  
## <a name="known-types-and-primitives"></a>Bekannte Typen und Primitive  
 Primitive Typen sowie bestimmte Typen, die als primitiv behandelt werden (z.&#160;B. <xref:System.DateTime> und <xref:System.Xml.XmlElement>) sind immer "bekannt" und müssen nie mithilfe dieses Mechanismus hinzugefügt werden. Arrays von primitiven Typen müssen allerdings explizit hinzugefügt werden. Die meisten Auflistungen werden als äquivalent mit Arrays betrachtet. (Nicht generische Auflistungen werden als äquivalent mit Arrays von <xref:System.Object>betrachtet). Ein Beispiel für die Verwendung von Primitiven, primitiven Arrays und primitiven Auflistungen finden Sie in Beispiel&#160;4.  
  
> [!NOTE]
> Im Gegensatz zu anderen primitiven Typen ist die <xref:System.DateTimeOffset> -Struktur standardmäßig kein bekannter Typ. Daher muss sie der Liste bekannter Typen manuell hinzugefügt werden.  
  
## <a name="examples"></a>Beispiele  
 In den folgenden Beispielen wird die Verwendung der <xref:System.Runtime.Serialization.KnownTypeAttribute> -Klasse veranschaulicht.  
  
#### <a name="example-1"></a>Beispiel 1  
 Es sind drei Klassen mit einer Vererbungsbeziehung gegeben.  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 Die folgende `CompanyLogo` -Klasse kann serialisiert werden. Sie kann jedoch nicht deserialisiert werden, wenn der `ShapeOfLogo` -Member auf ein `CircleType` -Objekt oder ein `TriangleType` -Objekt festgelegt wird, weil die Deserialisierungs-Engine keine Typen mit Datenverträgen namens "Circle" oder "Triangle" erkennt.  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 Im folgenden Code wird gezeigt, wie der `CompanyLogo` -Typ richtig geschrieben wird.  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 Jedes Mal, wenn der äußere Typ `CompanyLogo2` deserialisiert wird, wird die Deserialisierungs-Engine über `CircleType` und `TriangleType` informiert und kann daher die passenden Typen für die Datenverträge namens "Circle" und "Triangle" finden.  
  
#### <a name="example-2"></a>Beispiel 2  
 Im folgenden Beispiel ist sowohl `CustomerTypeA` als auch `CustomerTypeB` der Datenvertrag `Customer` zugeordnet. Trotz dieser Tatsache wird jedes Mal eine Instanz von `CustomerTypeB` erstellt, wenn ein `PurchaseOrder` -Objekt deserialisiert wird, weil die Deserialisierungs-Engine nur `CustomerTypeB` kennt.  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a>Beispiel 3  
 Im folgenden Beispiel speichert ein <xref:System.Collections.Hashtable> seinen Inhalt intern als <xref:System.Object>. Um eine Hashtabelle erfolgreich deserialisieren zu können, muss die Deserialisierungs-Engine die Gruppe möglicher Typen kennen, die hier vorkommen können. In diesem Fall wissen wir im Vorhinein, dass nur `Book` -Objekte und `Magazine` -Objekte im `Catalog`gespeichert werden. Daher werden sie mithilfe des <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attributs hinzugefügt.  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a>Beispiel 4  
 Im folgenden Beispiel wird eine Zahl und ein Vorgang, der mit der Zahl ausgeführt werden soll, in einem Datenvertrag gespeichert. Der `Numbers` -Datenmember kann eine ganze Zahl, ein Array von ganzen Zahlen oder ein Objekt des Typs <xref:System.Collections.Generic.List%601> sein, das ganze Zahlen enthält.  
  
> [!CAUTION]
> Dies funktioniert nur auf Clientseite, wenn zum Generieren eines WCF-Proxys SVCUTIL.EXE verwendet wird. SVCUTIL.EXE ruft Metadaten vom Dienst ab, einschließlich aller bekannter Typen. Ohne diese Informationen kann ein Client die Typen nicht deserialisieren.  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 Dies ist der Anwendungscode.  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a>Bekannte Typen, Vererbung und Schnittstellen  
 Wenn ein bekannter Typ mithilfe des `KnownTypeAttribute` -Attributs mit einem bestimmten Typ verknüpft wird, wird der bekannte Typ auch mit allen von diesem Typ abgeleiteten Typen verknüpft. Beachten Sie beispielsweise folgenden Code.  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 Die `DoubleDrawing` -Klasse erfordert nicht, dass das `KnownTypeAttribute` -Attribut mit `Square` und `Circle` im `AdditionalShape` -Feld verwendet wird, weil diese Attribute bereits auf die Basisklasse (`Drawing`) angewendet wurden.  
  
 Bekannte Typen können nur Klassen und Strukturen, nicht jedoch Schnittstellen, zugeordnet werden.  
  
## <a name="known-types-using-open-generic-methods"></a>Bekannte Typen, die offene generische Methoden verwenden  
 Es ist möglicherweise notwendig, einen generischen Typ als bekannten Typ hinzuzufügen. Ein offener generischer Typ kann dem `KnownTypeAttribute` -Attribut nicht als Parameter übergeben werden.  
  
 Dieses Problem lässt sich mithilfe eines alternativen Mechanismus lösen: Schreiben Sie eine Methode, die eine Liste derjenigen Typen zurückgibt, welche der Auflistung bekannter Typen hinzugefügt werden können. Wegen einigen Beschränkungen wird der Name der Methode dann als Zeichenfolgenargument für das `KnownTypeAttribute` -Attribut angegeben.  
  
 Diese Methode muss für den Typ vorhanden sein, auf den das `KnownTypeAttribute` -Attribut angewendet wird. Sie muss statisch sein, darf keine Parameter annehmen und muss ein Objekt zurückgeben, das der <xref:System.Collections.IEnumerable> -Schnittstelle von <xref:System.Type>zugewiesen werden kann.  
  
 Es ist nicht möglich, das `KnownTypeAttribute` -Attribut mit einem Methodennamen und `KnownTypeAttribute` -Attribute mit tatsächlichen Typen für den gleichen Typ zu kombinieren. Weiterhin ist es nicht möglich, mehr als ein `KnownTypeAttribute` -Attribut mit einem Methodennamen auf den gleichen Typ anzuwenden.  
  
 Siehe folgende Klasse.  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 Das `theDrawing` -Feld enthält Instanzen der generischen Klasse `ColorDrawing` und der generischen Klasse `BlackAndWhiteDrawing`, die beide von der generischen Klasse `Drawing`abgeleitet sind. Normalerweise müssen beide Klassen den bekannten Typen hinzugefügt werden, aber der folgende Code stellt keine für Attribute gültige Syntax dar.  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 Daher muss eine Methode erstellt werden, die diese Typen zurückgibt. Im folgenden Code wird gezeigt, wie dieser Typ richtig geschrieben wird.  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a>Weitere Verfahren zum Hinzufügen bekannter Typen  
 Darüber hinaus können bekannte Typen durch eine Konfigurationsdatei hinzugefügt werden. Dies ist hilfreich, wenn Sie nicht den Typ steuern, der bekannte Typen für die ordnungsgemäße Deserialisierung erfordert, z. b. bei der Verwendung von Typbibliotheken von Drittanbietern mit Windows Communication Foundation (WCF).  
  
 Die folgende Konfigurationsdatei zeigt, wie in einer Konfigurationsdatei ein bekannter Typ angegeben wird.  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 In der vorangegangenen Konfigurationsdatei wird ein Datenvertragstyp mit der Bezeichnung `MyCompany.Library.Shape` deklariert, um `MyCompany.Library.Circle` als bekannten Typ zu erhalten.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.KnownTypeAttribute>
- <xref:System.Collections.Hashtable>
- <xref:System.Object>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>
- [Bekannte Typen](../samples/known-types.md)
- [Datenvertragsäquivalenz](data-contract-equivalence.md)
- [Entwerfen von Dienstverträgen](../designing-service-contracts.md)
