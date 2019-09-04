---
title: 'Vorgehensweise: Ausführen einer polymorphen Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 49e0a6b44af0729959fabf6278cc6d8ecf37a16b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251512"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Vorgehensweise: Ausführen einer polymorphen Abfrage

In diesem Thema wird gezeigt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage mithilfe des [OfType](./language-reference/oftype-entity-sql.md) -Operators ausgeführt wird.

### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus

1. Fügen Sie dem Projekt das [Modell "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) " hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.

2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Ändern Sie das konzeptionelle Modell so, dass es eine Tabelle pro Hierarchie-Vererbung durch [führt, indem Sie die Schritte in Exemplarische Vorgehensweise Zuordnung von "Vererbungs Tabelle pro hier](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))Archie"

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Siehe auch

- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Entity SQL Language (Entity SQL-Sprache)](./language-reference/entity-sql-language.md)
