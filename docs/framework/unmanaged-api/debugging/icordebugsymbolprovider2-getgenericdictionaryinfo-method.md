---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34ed39d5fe9b820020d777fb3b33c950717059e9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645547"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode
Ruft eine generische Wörterbuchzuordnung ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppMemoryBuffer`  
 [out] Ein Zeiger auf die Adresse einer [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das die generische wörterbuchzuordnung enthält. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
 Die Zuordnung besteht aus zwei Abschnitten auf oberster Ebene:  
  
- Ein [Directory](#Directory) mit den relativen virtuellen Adressen (RVA) aller Wörterbücher, die in dieser Zuordnung enthalten.  
  
- Einem byteausgerichteten [Heap](#Heap) , die Informationen zur Objektinstanziierung enthält. Er beginnt unmittelbar nach dem letzten Verzeichniseintrag.  
  
<a name="Directory"></a>   
## <a name="the-directory"></a>Das Verzeichnis  
 Jeder Eintrag im Verzeichnis verweist auf einen Offset innerhalb des Heaps. Dieser Offset ist relativ zum Beginn des Heaps. Der Wert der einzelnen Einträge ist nicht notwendigerweise eindeutig. Es ist möglich, dass mehrere Verzeichniseinträge auf den gleichen Offset im Heap zeigen.  
  
 Der Verzeichnisteil der generischen Wörterbuchzuordnung weist die folgende Struktur auf:  
  
- Die ersten 4 Bytes enthalten die Anzahl der Wörterbucheinträge (d. h. die Anzahl der relativen virtuellen Adressen im Wörterbuch). Wir bezeichnen diesen Wert als *N*. Wenn das High-Bit festgelegt ist, werden die Einträge anhand der relativen virtuellen Adresse in aufsteigender Reihenfolge sortiert.  
  
- Die *N* Verzeichniseinträge folgen. Jeder Eintrag besteht aus 8 Bytes in zwei 4-Byte-Segmenten:  
  
    - Bytes 0-3: RVA; relative virtuelle Adresse des Wörterbuchs.  
  
    - Bytes 4-7: Offset; ein Offset relativ zum Beginn des Heaps.  
  
<a name="Heap"></a>   
## <a name="the-heap"></a>Der Heap  
 Die Größe des Heaps kann von einem StreamReader durch Subtrahieren der Länge des Datenstroms von der Verzeichnisgröße + 4 berechnet werden. Anders ausgedrückt:  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 Dabei ist die Verzeichnisgröße `N * 8`.  
  
 Das folgende Format wird für jedes Instanziierungsinformationselement auf dem Heap verwendet:  
  
- Die Länge dieses Instanziierungsinformationselements in Bytes im komprimierten ECMA-Metadatenformat. Der Wert schließt diese Längeninformationen aus.  
  
- Die Anzahl der generischen instanziierungstypen oder *T*, im komprimierten ECMA-Metadatenformat.  
  
- *T* Typen, die jeweils im ECMA-typsignaturformat dargestellt.  
  
 Die Berücksichtigung der Länge für jedes Heapelement ermöglicht eine einfache Sortierung des Verzeichnisabschnitts ohne Auswirkungen auf den Heap.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
