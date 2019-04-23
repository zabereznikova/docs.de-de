---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774328"
---
### <a name="encoderparameter-ctor-is-obsolete"></a>EncoderParameter ctor ist veraltet

|   |   |
|---|---|
|Details|Der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor ist jetzt veraltet und gibt Buildwarnungen aus, wenn er verwendet wird.|
|Vorschlag|Obwohl der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor weiterhin funktioniert, sollte stattdessen der folgende Konstruktor verwendet werden, um die veraltete Buildwarnung zu vermeiden, wenn Code mit .NET Framework 4.5-Tools erneut kompiliert wird: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
