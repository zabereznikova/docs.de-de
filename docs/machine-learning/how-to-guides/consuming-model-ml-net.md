---
title: Operationalisieren eines trainierten Machine Learning-Modells in Apps – ML.NET
description: Erfahren Sie, wie Sie mit ML.NET ein trainiertes und ausgewertetes Machine Learning-Modell in Anwendungen nutzen.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675133"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Operationalisieren eines trainierten Machine Learning-Modells in Apps – ML.NET

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Wenn Sie die Modellmetriken gut finden, ist es Zeit, das Modell zu „operationalisieren“. Das `model`-Objekt, das Sie erstellt haben, kann in verschiedenen Umgebungen genutzt, fortbestehen und wiederverwendet werden, wobei die gleichen Schritte angewendet werden, die es beim Training „gelernt“ hat.

Um das Modell in einer Datei zu speichern und erneut zu laden (möglicherweise in einem anderen Kontext), verwenden Sie das folgende Beispiel:

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
