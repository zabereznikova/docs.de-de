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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="0a5d9-103">Operationalisieren eines trainierten Machine Learning-Modells in Apps – ML.NET</span><span class="sxs-lookup"><span data-stu-id="0a5d9-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

<span data-ttu-id="0a5d9-104">Wenn Sie die Modellmetriken gut finden, ist es Zeit, das Modell zu „operationalisieren“.</span><span class="sxs-lookup"><span data-stu-id="0a5d9-104">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="0a5d9-105">Das `model`-Objekt, das Sie erstellt haben, kann in verschiedenen Umgebungen genutzt, fortbestehen und wiederverwendet werden, wobei die gleichen Schritte angewendet werden, die es beim Training „gelernt“ hat.</span><span class="sxs-lookup"><span data-stu-id="0a5d9-105">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="0a5d9-106">Um das Modell in einer Datei zu speichern und erneut zu laden (möglicherweise in einem anderen Kontext), verwenden Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0a5d9-106">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
