---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: 02ecaf56e845680472f42c04f3978e54e7a69272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791510"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode

Ruft eine generische Wörterbuchzuordnung ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a>Parameters

`ppMemoryBuffer`\
vorgenommen Ein Zeiger auf die Adresse eines [icorentbugmemorybuffer](icordebugmemorybuffer-interface.md) -Objekts, das die generische Wörterbuch Zuordnung enthält. Weitere Informationen finden Sie im Abschnitt Hinweise.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.

Die Zuordnung besteht aus zwei Abschnitten auf oberster Ebene:

- Ein [Verzeichnis](#Directory) mit den relativen virtuellen Adressen (RVA) aller Wörterbücher, die in dieser Zuordnung enthalten sind.

- Ein Byte-ausgerichteter [Heap](#Heap) , der objektinstanziationsinformationen enthält. Er beginnt unmittelbar nach dem letzten Verzeichniseintrag.

<a name="Directory"></a>

## <a name="the-directory"></a>Das Verzeichnis

Jeder Eintrag im Verzeichnis verweist auf einen Offset innerhalb des Heaps. Dieser Offset ist relativ zum Beginn des Heaps. Der Wert der einzelnen Einträge ist nicht notwendigerweise eindeutig. Es ist möglich, dass mehrere Verzeichniseinträge auf den gleichen Offset im Heap zeigen.

Der Verzeichnisteil der generischen Wörterbuchzuordnung weist die folgende Struktur auf:

- Die ersten 4 Bytes enthalten die Anzahl der Wörterbucheinträge (d. h. die Anzahl der relativen virtuellen Adressen im Wörterbuch). Dieser Wert wird als *N*bezeichnet. Wenn das hohe Bit festgelegt ist, werden die Einträge anhand der relativen virtuellen Adresse in aufsteigender Reihenfolge sortiert.

- Die *N* -Verzeichniseinträge folgen. Jeder Eintrag besteht aus 8 Bytes in zwei 4-Byte-Segmenten:

  - Bytes 0 - 3: RVA - die relative virtuelle Adresse des Wörterbuchs.

  - Bytes 4 - 7: Offset - ein Offset relativ zum Beginn des Heaps.

<a name="Heap"></a>

## <a name="the-heap"></a>Der Heap

Die Größe des Heaps kann von einem StreamReader durch Subtrahieren der Länge des Datenstroms von der Verzeichnisgröße + 4 berechnet werden. Anders ausgedrückt:

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

Dabei ist die Verzeichnisgröße `N * 8`.

Das folgende Format wird für jedes Instanziierungsinformationselement auf dem Heap verwendet:

- Die Länge dieses Instanziierungsinformationselements in Bytes im komprimierten ECMA-Metadatenformat. Der Wert schließt diese Längeninformationen aus.

- Die Anzahl der generischen instanziationstypen oder *T*im komprimierten ECMA-Metadatenformat.

- *T* -Typen, die jeweils im ECMA-Typsignatur Format dargestellt werden.

Die Berücksichtigung der Länge für jedes Heapelement ermöglicht eine einfache Sortierung des Verzeichnisabschnitts ohne Auswirkungen auf den Heap.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider2-Schnittstelle](icordebugsymbolprovider2-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
