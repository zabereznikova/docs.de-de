---
title: 'Gewusst wie: Aufrufen benutzerdefinierter Datenbankfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: f3177ab98382506770c4655c62573da5c1d96c69
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848755"
---
# <a name="how-to-call-custom-database-functions"></a>Gewusst wie: Aufrufen benutzerdefinierter Datenbankfunktionen

In diesem Thema wird das Aufrufen von benutzerdefinierten Funktionen beschrieben, die in der Datenbank in LINQ to Entities-Abfragen definiert werden.

Datenbankfunktionen, die von LINQ to Entities-Abfragen aufgerufen werden, werden in der Datenbank ausgeführt. Das Ausführen von Funktionen in der Datenbank kann die Anwendungsleistung verbessern.

Die folgende Prozedur stellt in knapper Form dar, wie eine benutzerdefinierte Datenbankfunktion aufgerufen wird. Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>So rufen Sie benutzerdefinierte Funktionen auf, die in der Datenbank definiert sind

1. Erstellen Sie in der Datenbank eine benutzerdefinierte Funktion.

     Weitere Informationen zum Erstellen benutzerdefinierter Funktionen in SQL Server finden Sie unter [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).

2. Beschreiben Sie in der Datenspeicherschema-Definitionssprache (SSDL) der EDMX-Datei eine Funktion. Der Name der Funktion muss mit der in der Datenbank deklarierten Funktion übereinstimmen.

     Weitere Informationen finden Sie unter [Funktionselement (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).

3. Fügen Sie einer Klasse im Anwendungscode eine entsprechende Methode hinzu, und übernehmen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode. Der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs sind die Namespacebezeichnung des konzeptionellen Modells bzw. der Funktionsname im konzeptionellen Modell. Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.

4. Rufen Sie die Methode in einer LINQ to Entities-Abfrage auf.  

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie eine benutzerdefinierte Datenbankfunktion innerhalb einer LINQ to Entities-Abfrage aufgerufen wird. Im Beispiel wird das Modell "School" verwendet. Informationen zum Schulmodell finden Sie unter [Erstellen der Schulbeispieldatenbank](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) und [Generieren der School .edmx-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).

Der folgende Code fügt die `AvgStudentGrade`-Funktion der Beispieldatenbank "School" hinzu.

> [!NOTE]
> Die Schritte zum Aufrufen einer benutzerdefinierten Datenbankfunktion sind unabhängig vom Datenbankserver identisch. Der folgende Code wird jedoch speziell für die Erstellung einer Funktion in einer SQL Server-Datenbank verwendet. Der Code zum Erstellen einer benutzerdefinierten Funktion in einem anderen Datenbankserver kann ggf. abweichen.

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a>Beispiel

Als Nächstes deklarieren Sie eine Funktion in der Speicherschemadefinitionssprache (SSDL) Ihrer *.edmx-Datei.* Der folgende Code `AvgStudentGrade` deklariert die Funktion in SSDL:

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a>Beispiel

Erstellen Sie nun eine Methode, und ordnen Sie sie der in der SSDL deklarierten Funktion zu. Die Methode in der folgenden Klasse wird der Funktion zugeordnet, die in der SSDL (oben) mithilfe eines <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> definiert wurde. Wird diese Methode aufgerufen, wird die entsprechende Funktion in der Datenbank ausgeführt.

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a>Beispiel

Rufen Sie schließlich die Methode in einer LINQ to Entities-Abfrage auf. Im folgenden Code werden die Nachnamen und Durchschnittsnoten von Schülern auf der Konsole angezeigt:

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)
