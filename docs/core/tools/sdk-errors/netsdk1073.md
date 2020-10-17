---
title: 'NETSDK1073: FrameworkReference wurde nicht erkannt'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn FrameworkReference nicht gefunden werden kann.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957089"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference wurde nicht erkannt

**Dieser Artikel gilt für:** ✔️ .NET 2.1.100 SDK und höhere Versionen

Dieser Fehler bedeutet in der Regel, dass es eine bestimmte FrameworkReference-Version gibt, die vom SDK nicht gefunden wird. Versuchen Sie, die Ordner *obj* und *bin* zu löschen und `dotnet restore` auszuführen, um die aktuellen Zielversionen noch mal herunterzuladen.

Alternativ könnte es ein Problem mit Ihrer Installation geben. Sorgen Sie also dafür, dass Sie die aktuelle Version von .NET und von Visual Studio verwenden.
