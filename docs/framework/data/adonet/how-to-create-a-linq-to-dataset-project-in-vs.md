---
title: Erstellen eines LINQ to DataSet Projekts in Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 91032766248b11e51b90aa788b1c64c140347c25
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802026"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Vorgehensweise: Erstellen eines LINQ to DataSet Projekts in Visual Studio

Die unterschiedlichen Arten von LINQ-Projekten benötigen bestimmte Assemblyverweise und importierte Namespaces (Visual Basic) oder [using](../../../csharp/language-reference/keywords/using-directive.md)-Anweisungen (C#). Die Mindestanforderung für LINQ ist ein Verweis auf " *System. Core. dll* " und eine `using`-Direktive für <xref:System.Linq>.

Diese Anforderungen werden standardmäßig bereitgestellt, wenn Sie ein C# neues Konsolen-App-Projekt in Visual Studio 2017 oder einer neueren Version erstellen. Wenn Sie ein Projekt von einer früheren Version von Visual Studio aktualisieren, müssen Sie diese LINQ-bezogenen Verweise möglicherweise manuell angeben.

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

1. Fügen Sie optional eine `using`-Direktive (oder `Imports`-Anweisung) für " **System. Data. Common** " oder " **System. Data. SqlClient**" hinzu, je nachdem, wie Sie eine Verbindung mit der Datenbank herstellen.

## <a name="see-also"></a>Siehe auch

- [Beginnen Sie mit LINQ to DataSet](getting-started-linq-to-dataset.md)
