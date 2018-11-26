---
title: Erstellen eines LINQ to DataSet-Projekt In Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297015"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Gewusst wie: Erstellen eines LINQ to DataSet-Projekt In Visual Studio

Die verschiedenen Typen von LINQ-Projekten erfordern bestimmte Assemblyverweise und importierten Namespaces (Visual Basic) oder [mit](../../../csharp/language-reference/keywords/using-directive.md) -Direktiven (c#). Die Mindestanforderung für LINQ ist ein Verweis auf *"System.Core.dll"* und `using` -Direktive für <xref:System.Linq>.

Diese Anforderungen werden standardmäßig bereitgestellt werden, wenn Sie ein neues C#-Konsolenanwendungsprojekt in Visual Studio 2017 erstellen. Wenn Sie ein Projekt von einer früheren Version von Visual Studio aktualisieren, müssen Sie möglicherweise diese LINQ-Verweise manuell bereitstellen.

LINQ to DataSet erfordert zwei zusätzliche Verweise auf *"System.Data.dll"* und *System.Data.DataSetExtensions.dll*.

> [!NOTE]
> Wenn Sie über eine Eingabeaufforderung erstellen, müssen Sie manuell die LINQ-bezogenen DLLs in verweisen *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>So aktivieren Sie die LINQ to DataSet-Funktionalität

Führen Sie diese Schritte zum Aktivieren von LINQ to DataSet-Funktionalität in einem vorhandenen Projekt.

1. Fügen Sie Verweise auf **System.Core**, **"System.Data"**, und **System.Data.DataSetExtensions**.

   In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **Verweise** Knoten, und wählen **Verweis hinzufügen**. In der **Verweis-Manager** wählen Sie im Dialogfeld **System.Core**, **"System.Data"**, und **System.Data.DataSetExtensions**. Klicken Sie auf **OK**.

1. Hinzufügen [mit](../../../csharp/language-reference/keywords/using-directive.md) Anweisungen (oder [Imports-Anweisungen](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) für **"System.Data"** und **"System.Linq"**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Fügen Sie optional eine `using` Richtlinie (oder `Imports` Anweisung) für **System.Data.Common** oder **"System.Data.SqlClient"**, je nachdem, wie Sie eine Verbindung mit der Datenbank herstellen.

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit LINQ to DataSet](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
