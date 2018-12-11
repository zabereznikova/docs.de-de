---
title: Grundlegende Typen (F#)
description: Entdecken Sie die grundlegenden, einfachen Typen, die in der Sprache F# verwendet werden.
ms.date: 07/09/2018
ms.openlocfilehash: a8a1154a211d8c87571b47cb41cb091096569472
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145123"
---
# <a name="basic-types"></a>Grundlegende Typen

Dieses Thema enthält die grundlegenden Typen, die definiert sind die F# Sprache. Diese Typen sind der wichtigste in F#, bilden die Grundlage für fast jede F#-Programm. Sie sind eine Obermenge von primitiven .NET-Typen.

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

> [!NOTE]
> Sie können Berechnungen mit ganzen Zahlen zu groß für den 64-Bit-Ganzzahl-Typ ausführen, indem Sie mit der [Bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) Typ. `bigint` ein Basistyp wurde nicht betrachtet werden. Es ist eine Abkürzung für `System.Numerics.BigInteger`.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
