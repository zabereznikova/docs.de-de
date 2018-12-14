---
title: Operationalisieren eines trainierten Machine Learning-Modells in Apps – ML.NET
description: Erfahren Sie, wie Sie mit ML.NET ein trainiertes und ausgewertetes Machine Learning-Modell in Anwendungen nutzen.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ff3f0a8856382d020129693bcf722f572fd87606
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131644"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Operationalisieren eines trainierten Machine Learning-Modells in Apps – ML.NET

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
