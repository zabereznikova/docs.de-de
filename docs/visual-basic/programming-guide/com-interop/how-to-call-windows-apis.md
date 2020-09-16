---
title: 'Vorgehensweise: Aufrufen von Windows-APIs'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 863986e94855e02e9fd04685f7dc3e8e7f7b1cc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548064"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)
In diesem Beispiel wird die- `MessageBox` Funktion in user32.dll definiert und aufgerufen und dann eine Zeichenfolge an Sie weitergeleitet.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System>-Namespace  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die Methode ist nicht statisch, ist abstrakt oder wurde zuvor definiert. Der übergeordnete Typ ist eine Schnittstelle, oder die Länge von *Name* oder *dllName* ist 0 (null). (<xref:System.ArgumentException>)  
  
- Der *Name* oder der *dllName* ist `Nothing` . (<xref:System.ArgumentNullException>)  
  
- Der enthaltende Typ wurde zuvor mit `CreateType` erstellt. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Siehe auch

- [Genauere Betrachtung von Plattformaufrufen](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Beispiele für Plattformaufrufe](../../../framework/interop/platform-invoke-examples.md)
- [Verwenden nicht verwalteter DLL-Funktionen](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definieren einer Methode mittels Reflektionsausgabe](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](walkthrough-calling-windows-apis.md)
- [COM-Interop](index.md)
