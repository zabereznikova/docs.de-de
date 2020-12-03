---
title: 'NETSDK1073: FrameworkReference wurde nicht erkannt'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn FrameworkReference nicht gefunden werden kann.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713027"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference wurde nicht erkannt

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höher

Dieser Fehler bedeutet in der Regel, dass es eine bestimmte FrameworkReference-Version gibt, die vom SDK nicht gefunden wird. Versuchen Sie, die Ordner *obj* und *bin* zu löschen und `dotnet restore` auszuführen, um die aktuellen Zielversionen noch mal herunterzuladen.

Alternativ könnte es ein Problem mit Ihrer Installation geben. Sorgen Sie also dafür, dass Sie die aktuelle Version von .NET und von Visual Studio verwenden.
