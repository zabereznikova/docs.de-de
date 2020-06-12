---
title: Verarbeiten der XML-Datei – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 1e3d96f9398f2c08ed715111f01987e2d1948439
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287258"
---
# <a name="process-the-xml-file-c-programming-guide"></a>Verarbeiten der XML-Datei (C#-Programmierhandbuch)

Für jedes Konstrukt, das zum Generieren einer Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert. (Weitere Informationen darüber, wie Code mit Tags versehen werden kann, finden Sie unter [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md).) Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert. Programme, die die XML-Datei verarbeiten, können mithilfe der ID-Zeichenfolge das entsprechende .NET -Metadatenelement oder -Reflektionselement identifizieren, für das die Dokumentation gilt.

## <a name="id-strings"></a>ID-Zeichenfolgen

Die XML-Datei ist keine hierarchische Darstellung des Codes. Es handelt sich um eine flache Liste mit einer generierten ID für jedes Element.

Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:

- Es befindet sich kein Leerraum in der Zeichenfolge.

- Der erste Teil der Zeichenfolge kennzeichnet die Art des Members durch ein einzelnes Zeichen, dem ein Doppelpunkt folgt. Die folgenden Membertypen werden verwendet:

    |Zeichen|Memberart|Hinweise|
    |---------------|-----------------|-|
    |N|namespace|Einem Namespace können keine Dokumentationskommentare hinzugefügt werden. Falls unterstützt, können jedoch cref-Verweise hinzugefügt werden.|
    |T|Typ|Ein Typ kann eine Klasse, eine Schnittstelle, eine Struktur, eine Enumeration oder ein Delegat sein.|
    |F|Feld|
    |P|property|Schließt Indexer und andere indizierte Eigenschaften ein|
    |M|Methode|Schließt spezielle Methoden wie Konstruktoren und Operatoren ein|
    |E|event|
    |!|Fehlerzeichenfolge|Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen. Vom C#-Compiler werden Fehlerinformationen für Links erstellt, die nicht aufgelöst werden können.|

- Beim zweiten Teil der Zeichenfolge handelt es sich um den vollqualifizierten Namen eines Elements, beginnend mit dem Namespace-Stammverzeichnis. Der Name des Elements, der oder die einschließenden Typen und der Namespace sind durch Punkte getrennt. Wenn der Name des Elements selbst Punkte enthält, werden sie durch ein Rautezeichen (#) ersetzt. Es wird vorausgesetzt, dass kein Element direkt im Namen ein Rautezeichen enthält. Der vollqualifizierte Name des String-Konstruktors lautet beispielsweise „System.String.#ctor“.

- Bei Eigenschaften und Methoden folgt die in Klammern eingeschlossene Parameterliste. Wenn keine Parameter vorhanden sind, werden keine Klammern verwendet. Die Parameter werden durch Kommas voneinander getrennt. Die Codierung jedes Parameters erfolgt genau wie die Codierung in einer .NET-Signatur:

  - Basistypen. Reguläre Typen (ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE) werden als vollqualifizierter Name des Typs dargestellt.

  - Intrinsische Typen (z. B. ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF, und ELEMENT_TYPE_VOID) werden als vollqualifizierter Name des entsprechenden vollständigen Typnamens dargestellt. Als Beispiel sei hier System.Int32 oder System.TypedReference genannt.

  - ELEMENT_TYPE_PTR wird als \* dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_BYREF wird als \@ dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_PINNED wird als ^ dargestellt, das auf den geänderten Typ folgt. Dies wird nie vom C#-Compiler generiert.

  - ELEMENT_TYPE_CMOD_REQ wird als &#124; und vollqualifizierter Name der Modifiziererklasse dargestellt, das bzw. der auf den geänderten Typ folgt. Dies wird nie vom C#-Compiler generiert.

  - ELEMENT_TYPE_CMOD_OPT wird als ! mit nachstehendem vollqualifizierten Namen der Modifiziererklasse dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_SZARRAY wird als [] dargestellt, das auf den Elementtyp des Arrays folgt.

  - ELEMENT_TYPE_GENERICARRAY wird als [?] dargestellt, das auf den Elementtyp des Arrays folgt. Dies wird nie vom C#-Compiler generiert.

  - ELEMENT_TYPE_ARRAY wird als [*lowerbound*:`size`,*lowerbound*:`size`] dargestellt, wobei die Anzahl von Kommas als Rang minus 1 berechnet wird und die untere Grenze sowie die Größe jeder Dimension – sofern bekannt – dezimal dargestellt werden. Wenn die untere Grenze oder die Größe nicht angegeben ist, wird sie ausgelassen. Wenn die untere Grenze und die Größe für eine bestimmte Dimension ausgelassen werden, kann der Doppelpunkt (:) ebenfalls ausgelassen werden. [1:,1:] ist beispielsweise ein zweidimensionales Array mit 1 als unterer Grenze und nicht angegebenen Größen.

  - ELEMENT_TYPE_FNPTR wird als „=FUNC:`type`(*signature*)“ dargestellt, wobei `type` den Rückgabetyp angibt und es sich bei *signature* um die Argumente der Methode handelt. Sind keine Argumente vorhanden, werden keine Klammern verwendet. Dies wird nie vom C#-Compiler generiert.

  Die folgenden Signaturkomponenten werden nicht dargestellt, weil sie nicht zur Unterscheidung überladener Methoden verwendet werden:

  - Aufrufkonvention

  - Rückgabetyp

  - ELEMENT_TYPE_SENTINEL

- Nur für Konvertierungsoperatoren (`op_Implicit` und `op_Explicit`) wird der Rückgabewert der Methode als „~“ gefolgt vom Rückgabewert codiert.

- Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und dann eine Zahl, mit der die Anzahl generischer Typparameter angegeben wird. Zum Beispiel:

     ``<member name="T:SampleClass`2">`` ist das Tag für einen Typ, der als `public class SampleClass<T, U>` definiert ist.

     Bei Methoden, die generische Typen als Parameter verwenden, werden die generischen Parameter des Typs als Zahlen mit vorangestelltem Backticks angegeben (z. B. \`0,\`1). Jede Zahl stellt eine bei 0 beginnende Arraynotation für die generischen Parameter des Typs dar.

## <a name="examples"></a>Beispiele

In den folgenden Beispielen wird veranschaulicht, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert werden:

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [-doc (C#-Compileroptionen)](../../language-reference/compiler-options/doc-compiler-option.md)
- [XML-Dokumentationskommentare](./index.md)
