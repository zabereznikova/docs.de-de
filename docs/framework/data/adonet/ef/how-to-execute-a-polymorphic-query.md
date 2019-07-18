---
title: 'Vorgehensweise: Ausführen einer polymorphen Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 08ae5722267ef781ed6bee59c7895269f63a75e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606189"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Vorgehensweise: Ausführen einer polymorphen Abfrage

In diesem Thema wird gezeigt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen mit der [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) Operator.

### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus

1. Hinzufügen der [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) zu Ihrem Projekt und konfigurieren Sie das Projekt zur Verwendung von Entity Framework. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Ändern Sie das konzeptionelle Modell, um eine Tabelle pro Hierarchie-Vererbung verfügen, indem Sie die Schritte in [Exemplarische Vorgehensweise: Zuordnen von Vererbung - ' Tabelle pro Hierarchie](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein OFTYPE-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Siehe auch

- [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
