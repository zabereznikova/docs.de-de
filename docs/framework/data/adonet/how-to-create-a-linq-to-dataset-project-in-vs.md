---
title: Erstellen eines LINQ to DataSet Projekts in Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783775"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Vorgehensweise: Erstellen eines LINQ to DataSet Projekts in Visual Studio

Die unterschiedlichen Arten von LINQ-Projekten benötigen bestimmte Assemblyverweise und importierte Namespaces (Visual Basic) oder [using](../../../csharp/language-reference/keywords/using-directive.md)-Anweisungen (C#). Die Mindestanforderung für LINQ ist ein Verweis auf " *System. Core. dll* " `using` und eine <xref:System.Linq>-Direktive für.

Diese Anforderungen werden standardmäßig bereitgestellt, wenn Sie ein C# neues Konsolen-App-Projekt in Visual Studio 2017 erstellen. Wenn Sie ein Projekt von einer früheren Version von Visual Studio aktualisieren, müssen Sie diese LINQ-bezogenen Verweise möglicherweise manuell angeben.

LINQ to DataSet erfordert zwei zusätzliche Verweise auf *System. Data. dll* und *System. Data. DataSetExtensions. dll*.

> [!NOTE]
> Wenn Sie von einer Eingabeaufforderung aus erstellen, müssen Sie manuell auf die LINQ-bezogenen DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*verweisen.

## <a name="to-enable-linq-to-dataset-functionality"></a>So aktivieren Sie die LINQ to DataSet-Funktionalität

Führen Sie die folgenden Schritte aus, um LINQ to DataSet Funktionalität in einem vorhandenen-Projekt zu aktivieren.

1. Fügen Sie Verweise auf **System. Core**, **System. Data**und **System. Data. DataSetExtensions**hinzu.

   Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Knoten **Verweise** , und wählen Sie **Verweis hinzufügen**aus. Wählen Sie im Dialogfeld **Verweis-Manager** die Option **System. Core**, **System. Data**und **System. Data. DataSetExtensions**aus. Klicken Sie auf **OK**.

1. Fügen Sie [using](../../../csharp/language-reference/keywords/using-directive.md) -Direktiven (oder [Imports-Anweisungen](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) für **System. Data** und **System. Linq**hinzu.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Optional können Sie eine `using` -Direktive `Imports` (oder-Anweisung) für **System. Data. Common** oder **System. Data. SqlClient**hinzufügen, je nachdem, wie Sie eine Verbindung mit der Datenbank herstellen.

## <a name="see-also"></a>Siehe auch

- [Beginnen Sie mit LINQ to DataSet](getting-started-linq-to-dataset.md)
