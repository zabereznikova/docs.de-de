---
title: 'Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: de568c3273d4d040c6566136e5d59e2155b86f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Gewusst wie: Aufrufen von Windows-APIs (Visual Basic)
In diesem Beispiel definiert und ruft die `MessageBox` -Funktion in "User32.dll" und dann eine Zeichenfolge an diese übergibt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System>-Namespace  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Methode ist nicht statisch, ist abstrakt oder wurde bereits definiert. Der übergeordnete Typ ist eine Schnittstelle oder die Länge des *Namen* oder *DLL-Namen* 0 (null). (<xref:System.ArgumentException>)  
  
-   Die *Namen* oder *DLL-Namen* ist `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Der enthaltende Typ wurde zuvor mit `CreateType` erstellt. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Siehe auch  
 [Genauere Betrachtung von Plattformaufrufen](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [Beispiele für Plattformaufrufe](../../../framework/interop/platform-invoke-examples.md)  
 [Verwenden nicht verwalteter DLL-Funktionen](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [Definieren eine Methode mit Reflektionsausgabe](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
