---
title: 'NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn ein Projekt ein veraltetes CLI-Tool für .NET enthält.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713118"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höher

Wenn das .NET SDK die Warnung NETSDK1059 ausgibt, enthält Ihr Projekt ein veraltetes CLI-Tool für .NET. Seit .NET Core 2.1 sind diese Tools im .NET SDK enthalten, und im Projekt muss nicht explizit darauf verwiesen werden. Weitere Informationen zur Migration zu .NET Core 2.1 finden Sie [hier](https://aka.ms/dotnetclitools-in-box).
