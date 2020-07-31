---
title: 'Vorgehensweise: Analysieren einer Zeichenfolge (C#)'
description: Hier erfahren Sie, wie Sie eine Zeichenfolge analysieren, um in C# eine XML-Baum zu erstellen. Hier erfahren Sie, wie Sie auf bestimmte Daten im analysierten XML-Code zugreifen.
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: a4664e090b6a44c52c519e61b66ccdc5d59a71f1
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104816"
---
# <a name="how-to-parse-a-string-c"></a>Vorgehensweise: Analysieren einer Zeichenfolge (C#)

In diesem Thema wird erläutert, wie Sie in C# eine XML-Struktur erstellen können.

## <a name="example"></a>Beispiel

Der folgende C#-Code zeigt das Analysieren einer XML-Zeichenfolge:

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

Der Stammknoten `Contacts` verfügt über zwei `Contact`-Knoten. Um auf bestimmte Daten in der analysierten XML zuzugreifen, verwenden Sie die Methode [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements), die in diesem Fall die untergeordneten Elemente des Stammknotens `Contacts` zurückgibt. Im folgenden Beispiel wird der erste `Contact`-Knoten in die Konsole geschrieben:

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Suchen nach einem Element mit bestimmten Attributen (C#)](how-to-find-an-element-with-a-specific-attribute.md)
