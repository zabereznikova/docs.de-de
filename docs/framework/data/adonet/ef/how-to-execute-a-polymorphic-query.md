---
title: 'Vorgehensweise: Ausführen einer polymorphen Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545336"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Vorgehensweise: Ausführen einer polymorphen Abfrage

In diesem Thema wird gezeigt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage mithilfe des [OfType](./language-reference/oftype-entity-sql.md) -Operators ausgeführt wird.

### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus

1. Fügen Sie dem Projekt das [Modell "School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) " hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Ändern Sie das konzeptionelle Modell so, dass es eine "Tabelle pro Hierarchie"-Vererbung durchführt, indem Sie die Schritte unter Exemplarische Vorgehensweise [: Mapping Vererbungs Tabelle pro Hierarchie](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))ausführen

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Siehe auch

- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Entity SQL-Sprache](./language-reference/entity-sql-language.md)
