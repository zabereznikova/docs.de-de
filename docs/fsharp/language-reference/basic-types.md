---
title: Grundlegende Typen
description: 'Entdecken Sie die grundlegenden Typen, die in der Sprache F # verwendet werden.'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557697"
---
# <a name="basic-types"></a>Grundlegende Typen

In diesem Thema werden die grundlegenden Typen aufgeführt, die in der Sprache F # definiert sind. Diese Typen sind die grundlegendsten in f # und bilden die Grundlage für fast alle f #-Programme. Dabei handelt es sich um eine supermenge von primitiven .NET-Typen.

|type|.NET-Typ|BESCHREIBUNG|Beispiel|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|Mögliche Werte sind `true` und `false`.|`true`/`false`|
|`byte`|<xref:System.Byte>|Werte zwischen 0 und 255.|`1uy`|
|`sbyte`|<xref:System.SByte>|Werte von-128 bis 127.|`1y`|
|`int16`|<xref:System.Int16>|Werte von-32768 bis 32767.|`1s`|
|`uint16`|<xref:System.UInt16>|Werte zwischen 0 und 65535.|`1us`|
|`int`|<xref:System.Int32>|Werte von-2.147.483.648 bis 2.147.483.647.|`1`|
|`uint`|<xref:System.UInt32>|Werte zwischen 0 und 4.294.967.295.|`1u`|
|`int64`|<xref:System.Int64>|Werte von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807.|`1L`|
|`uint64`|<xref:System.UInt64>|Werte zwischen 0 und 18446744073709551615.|`1UL`|
|`nativeint`|<xref:System.IntPtr>|Ein nativer Zeiger als Ganzzahl mit Vorzeichen.|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|Ein nativer Zeiger als ganze Zahl ohne Vorzeichen.|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|Ein Gleit Komma Datentyp mit mindestens 28 signifikanten Ziffern.|`1.0`|
|`float`, `double`|<xref:System.Double>|Ein 64-Bit-Gleit kommatyp.|`1.0`|
|`float32`, `single`|<xref:System.Single>|Ein 32-Bit-Gleit kommatyp.|`1.0f`|
|`char`|<xref:System.Char>|Unicode-Zeichen Werte.|`'c'`|
|`string`|<xref:System.String>|Unicode-Text.|`"str"`|
|`unit`|nicht zutreffend|Gibt an, dass kein tatsächlicher Wert vorhanden ist. Der-Typ verfügt nur über einen formalen Wert, der angegeben wird `()` . Der Einheits Wert `()` wird häufig als Platzhalter verwendet, bei dem ein Wert benötigt wird, aber kein echter Wert verfügbar oder sinnvoll ist.|`()`|

> [!NOTE]
> Sie können Berechnungen mit ganzen Zahlen für den ganzzahligen 64-Bit-Typ durchführen, indem Sie den [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) -Typ verwenden. `bigint` wird nicht als Basistyp betrachtet. Dies ist eine Abkürzung für `System.Numerics.BigInteger` .

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
