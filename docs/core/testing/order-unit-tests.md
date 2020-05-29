---
title: Festlegen einer Reihenfolge von Komponententests
description: Erfahren Sie, wie Sie mit .NET Core eine Reihenfolge von Komponententests festlegen.
author: IEvangelist
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: ce0d01c924075ffcc9ad49ef8aca49222c10c921
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83704532"
---
# <a name="order-unit-tests"></a>Festlegen einer Reihenfolge von Komponententests

Gelegentlich kann es erforderlich sein, dass Komponententests in einer bestimmten Reihenfolge ausgeführt werden. Im Idealfall sollte die Reihenfolge, in der Komponententests ausgeführt werden, _keine_ Rolle spielen, und es ist ein [bewährte Methode](unit-testing-best-practices.md), das Festlegen einer Reihenfolge von Komponententests zu vermeiden. Nichtsdestoweniger kann es im Einzelfall erforderlich sein. In diesem Artikel erfahren Sie, wie Sie die Reihenfolge von Komponententests festlegen.

Wenn Sie lieber den Quellcode durchsuchen möchten, finden Sie weitere Informationen im Beispielrepository [Festlegen der Reihenfolge von .NET Core-Komponententests](/samples/dotnet/samples/order-unit-tests-cs).

> [!TIP]
> Zusätzlich zu den in diesem Artikel beschriebenen Funktionen zum Festlegen der Reihenfolge sollten Sie das [Erstellen benutzerdefinierter Wiedergabelisten mit Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) als Alternative berücksichtigen.

:::zone pivot="mstest"

## <a name="order-alphabetically"></a>Alphabetisches Sortieren

Mit MSTest werden Tests automatisch nach ihrem Testnamen geordnet.

> [!NOTE]
> Ein Test mit dem Namen `Test14` wird vor `Test2` ausgeführt, obwohl die Zahl `2` kleiner als `14` ist. Dies liegt daran, dass beim Festlegen der Reihenfolge der Textname des Tests verwendet wird.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

Das xUnit-Testframework ermöglicht eine höhere Genauigkeit und Steuerung der Testreihenfolge. Sie implementieren die Schnittstellen `ITestCaseOrderer` und `ITestCollectionOrderer`, um die Reihenfolge von Testfällen für eine Klasse oder Testsammlungen zu steuern.

## <a name="order-by-test-case-alphabetically"></a>Alphabetisches Sortieren nach Testfall

Um Testfälle nach dem Methodennamen zu sortieren, implementieren Sie den `ITestCaseOrderer` und stellen einen Sortiermechanismus bereit.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

In einer Testklasse legen Sie dann die Testfallreihenfolge mit dem `TestCaseOrdererAttribute` fest.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a>Alphabetisches Sortieren nach Sammlung

Um Testsammlungen nach dem Anzeigenamen zu sortieren, implementieren Sie den `ITestCollectionOrderer` und stellen einen Sortiermechanismus bereit.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

Da Testsammlungen möglicherweise parallel ausgeführt werden, müssen Sie die Testparallelisierung der Sammlungen mit dem `CollectionBehaviorAttribute` explizit deaktivieren. Geben Sie dann die Implementierung des `TestCollectionOrdererAttribute` an.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a>Sortieren nach benutzerdefiniertem Attribut

Um xUnit-Tests mit benutzerdefinierten Attributen zu sortieren, benötigen Sie zuerst ein Attribut, auf das Sie sich verlassen können. Definieren Sie wie folgt ein `TestPriorityAttribute`:

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

Erwägen Sie als Nächstes die folgende `PriorityOrderer`-Implementierung der `ITestCaseOrderer`-Schnittstelle:

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

In einer Testklasse legen Sie dann die Testfallreihenfolge mit dem `TestCaseOrdererAttribute` auf `PriorityOrderer` fest.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a>Sortieren nach Priorität

Zum expliziten Sortieren von Tests stellt NUnit ein [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute) bereit. Tests mit diesem Attribut werden vor Tests ohne gestartet. Der Wert für die Reihenfolge wird verwendet, um die Reihenfolge zum Ausführen der Komponententests zu bestimmen.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Bewährte Methoden für Komponententests](unit-testing-best-practices.md)
