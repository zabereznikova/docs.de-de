---
title: Enumerationsformatzeichenfolgen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: c32fd9d59f61b6befe94ff9eb85b0c39ce926adb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348267"
---
# <a name="enumeration-format-strings"></a>Enumerationsformatzeichenfolgen

Sie können die <xref:System.Enum.ToString%2A?displayProperty=nameWithType>-Methode verwenden, um ein neues Zeichenfolgenobjekt zu erstellen, das den numerischen, den Hexadezimal- oder den Zeichenfolgenwert eines Enumerationsmembers darstellt. Diese Methode akzeptiert eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, der zurückgegeben werden soll.

In den folgenden Abschnitten werden die Enumerationsformatzeichenfolgen sowie die Werte aufgeführt, die diese zurückgeben. Bei diesen Formatbezeichnern wird die Groß- und Kleinschreibung nicht berücksichtigt.

## <a name="g-or-g"></a>G oder g

Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an, zeigt andernfalls den ganzzahligen Wert der aktuellen Instanz an. Wenn die Enumeration mit festgelegtem **Flags**-Attribut definiert ist, werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn das **Flags**-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt. Das folgende Beispiel veranschaulicht den Formatbezeichner „G“.

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a>F oder f

Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an. Wenn der Wert vollständig als Summe der Einträge in der Enumeration angezeigt werden kann (selbst wenn das **Flags**-Attribut nicht vorhanden ist), werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn der Wert nicht vollständig durch die Enumerationseinträge ermittelt werden kann, wird der Wert als ganzzahliger Wert formatiert. Das folgende Beispiel veranschaulicht den Formatbezeichner „F“.

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a>D oder d

Zeigt den Enumerationseintrag in der kürzestmöglichen Darstellung als ganzzahligen Wert an. Das folgende Beispiel veranschaulicht den Formatbezeichner „D“.

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a>X oder x

Zeigt den Enumerationseintrag als Hexadezimalwert an. Der Wert wird ggf. mit führenden Nullen dargestellt, um sicherzustellen, dass die resultierende Zeichenfolge für jedes Byte im [zugrunde liegenden numerischen Typ](xref:System.Enum.GetUnderlyingType%2A) des Enumerationstyps über zwei Zeichen verfügt. Das folgende Beispiel veranschaulicht den Formatbezeichner „X“. Der zugrunde liegende Typ sowohl für <xref:System.ConsoleColor> als auch für <xref:System.IO.FileAttributes> in diesem Beispiel ist <xref:System.Int32> oder ein Integertyp mit 32 Bit (bzw. 4 Byte), wodurch eine Ergebniszeichenfolge mit 8 Zeichen erzeugt wird.

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]      
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine Enumeration namens `Colors`, die aus drei Einträgen besteht: `Red`, `Blue` und `Green`.

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

Nachdem die Enumeration definiert wurde, kann auf folgende Weise eine Instanz deklariert werden.

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

Dann kann die `Color.ToString(System.String)`-Methode verwendet werden, um den Enumerationswert je nach übergebenem Formatbezeichner auf verschiedene Arten anzuzeigen.

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a>Siehe auch

- [Formatierung von Typen](formatting-types.md)
