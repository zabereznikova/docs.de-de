---
title: Primitive Typen (F#)
description: Ermitteln Sie die grundlegenden primitiven Typen, die in der Programmiersprache f# verwendet werden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7832151ee211f56547ecad98fc31f1454cb18870
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="primitive-types"></a>Primitive Typen

Dieses Thema enthält die grundlegenden primitiven Typen, die in der Programmiersprache f# verwendet werden. Darüber hinaus werden die entsprechenden Typen in .NET und die minimalen und maximalen Werte für jeden Typ bereitgestellt.

## <a name="summary-of-primitive-types"></a>Zusammenfassung der primitiven Typen
In der folgenden Tabelle werden die Eigenschaften von primitiven f#-Typen zusammengefasst.

|Typ|.NET-Typ|Beschreibung|
|----|---------|-----------|
|`bool`|`System.Boolean`|Mögliche Werte sind `true` und `false`.|
|`byte`|`System.Byte`|Werte von 0 bis 255.|
|`sbyte`|`System.SByte`|Werte von-128 bis 127.|
|`int16`|`System.Int16`|Werte von-32768 bis 32767.|
|`uint16`|`System.UInt16`|Werte von 0 bis 65535.|
|`int`|`System.Int32`|Werte von -2.147.483.648 bis 2.147.483.647.|
|`uint32`|`System.UInt32`|Werte zwischen 0 und 4.294.967.295 ein.|
|`int64`|`System.Int64`|Werte von -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807.|
|`uint64`|`System.UInt64`|Werte von 0 bis 18.446.744.073.709.551.615.|
|`nativeint`|`System.IntPtr`|Ein systemeigener Zeiger als eine Ganzzahl mit Vorzeichen.|
|`unativeint`|`System.UIntPtr`|Ein systemeigener Zeiger als ganze Zahl ohne Vorzeichen.|
|`char`|`System.Char`|Unicode-Zeichenwerte.|
|`string`|`System.String`|Unicode-Text.|
|`decimal`|`System.Decimal`|Ein Gleitkommawert-Datentyp, der mindestens 28 signifikante Ziffern umfasst.|
|`unit`|Nicht zutreffend|Gibt das Fehlen eines tatsächlichen Werts. Der Typ hat nur einen formalen Wert ab, die gekennzeichnet ist `()`. Den Einheitswert `()`, wird häufig als Platzhalter, in dem ein Wert benötigt wird, aber keine echten Wert verfügbar ist oder sinnvoll, verwendet.|
|`void`|`System.Void`|Gibt an, kein Typ oder Wert.|
|`float32, single`|`System.Single`|Eine 32-Bit-Gleitkommatyp.|
|`float, double`|`System.Double`|Eine 64-Bit-Gleitkommatyp.|

>[!NOTE]
Sie können Berechnungen mit ganzen Zahlen zu groß für den 64-Bit-Ganzzahl-Typ ausführen, mit der ["bigint"](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) Typ. `bigint` einen primitiven Typ ist nicht berücksichtigt werden; Es ist eine Abkürzung für `System.Numerics.BigInteger`.

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
