---
title: 'NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn ein Projekt ein veraltetes CLI-Tool für .NET enthält.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957090"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET

**Dieser Artikel gilt für:** ✔️ .NET 2.1.100 SDK und höhere Versionen

Wenn das .NET SDK die Warnung NETSDK1059 ausgibt, enthält Ihr Projekt ein veraltetes CLI-Tool für .NET. Ab .NET 2.1 sind diese Tools im .NET SDK enthalten, und im Projekt müssen keine expliziten Verweise darauf eingeschlossen werden. Weitere Informationen zur Migration zu .NET 2.1 finden Sie [hier](https://aka.ms/dotnetclitools-in-box).
