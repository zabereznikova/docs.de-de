---
title: Grundlegende Typen (f#)
description: Entdecken Sie die grundlegenden, einfachen Typen, die in der Sprache f# verwendet werden.
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44202205"
---
# <a name="basic-types"></a>Grundlegende Typen

Dieses Thema enthält die grundlegenden Typen, die in der F#-Sprache definiert sind. Diese Typen sind der wichtigste in f#, bilden die Grundlage für fast jede f#-Programm. Sie sind eine Obermenge von primitiven .NET-Typen.

|Typ|.NET-Typ|Beschreibung|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|Mögliche Werte sind `true` und `false`.|
|`byte`|<xref:System.Byte>|Die Werte von 0 bis 255.|
|`sbyte`|<xref:System.SByte>|Werte von-128 bis 127.|
|`int16`|<xref:System.Int16>|Werte von-32768 bis 32767.|
|`uint16`|<xref:System.UInt16>|Werte von 0 bis 65535.|
|`int`|<xref:System.Int32>|Die Werte von-2.147.483.648 bis 2.147.483.647.|
|`uint32`|<xref:System.UInt32>|Die Werte von 0 bis 4.294.967.295.|
|`int64`|<xref:System.Int64>|Die Werte von-9.223.372.036.854.775.808 bis + 9.223.372.036.854.775.807.|
|`uint64`|<xref:System.UInt64>|Werte von 0 bis 18.446.744.073.709.551.615.|
|`nativeint`|<xref:System.IntPtr>|Ein systemeigener Zeiger als eine Ganzzahl mit Vorzeichen.|
|`unativeint`|<xref:System.UIntPtr>|Ein systemeigener Zeiger als ganze Zahl ohne Vorzeichen.|
|`char`|<xref:System.Char>|Unicode-Zeichenwerte.|
|`string`|<xref:System.String>|Unicode-Text.|
|`decimal`|<xref:System.Decimal>|Ein Gleitkommawert-Datentyp, der mindestens 28 signifikante Ziffern umfasst.|
|`unit`|Nicht zutreffend|Gibt das Fehlen eines tatsächlichen Werts. Der Typ aufweist, nur eine formale Wert, der gekennzeichnet ist `()`. Der Einheitenwert `()`, dient häufig als Platzhalter, in dem ein Wert erforderlich ist, aber keine echter Wert verfügbar ist oder sinnvoll.|
|`void`|<xref:System.Void>|Gibt an, kein Typ oder Wert.|
|`float32`, `single`|<xref:System.Single>|Eine 32-Bit-Gleitkommatyp.|
|`float`, `double`|<xref:System.Double>|Eine 64-Bit-Gleitkommatyp.|

>[!NOTE]
Sie können Berechnungen mit ganzen Zahlen zu groß für den 64-Bit-Ganzzahl-Typ ausführen, indem Sie mit der [Bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) Typ. `bigint` ein Basistyp wurde nicht betrachtet werden. Es ist eine Abkürzung für `System.Numerics.BigInteger`.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
