---
title: 'NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn ein Projekt ein veraltetes CLI-Tool für .NET enthält.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: bba5f4dafa346d81274541f3c40ecc5ed6fff8ab
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190324"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höher

Wenn das .NET SDK die Warnung NETSDK1059 ausgibt, enthält Ihr Projekt ein veraltetes CLI-Tool für .NET. Seit .NET Core 2.1 sind diese Tools im .NET SDK enthalten, und im Projekt muss nicht explizit darauf verwiesen werden. Weitere Informationen zur Migration zu .NET Core 2.1 finden Sie [hier](../../migration/20-21.md).
