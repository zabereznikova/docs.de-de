---
title: 'Vorgehensweise: Unterstützen von COM-Interop durch das Anzeigen einzelner Windows Forms in einem eigenen Thread'
ms.date: 03/30/2017
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 90bbd7df45424f8513598e9d7439d8ae6bf6f52c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040312"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Vorgehensweise: Unterstützung von COM-Interop durch Anzeigen jedes Windows Forms in einem eigenen Thread

Sie können Probleme mit der COM-Interoperabilität beheben, indem Sie das Formular in einer .NET Framework-Nachrichten Schleife anzeigen, die <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> Sie mit der-Methode erstellen können.

Damit ein Windows Form aus einer COM-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie das Formular in einer Windows Forms-Nachrichtenschleife ausführen. Hierzu können Sie einen der folgenden Ansätze verwenden:

- Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>-Methode, um das Windows Form anzuzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Unterstützung von COM-Interop durch Anzeigen eines Windows Forms mit der](com-interop-by-displaying-a-windows-form-shadow.md)Show Dialog-Methode.

- Zeigen Sie jedes Windows Form in einem separaten Thread an.

In Visual Studio wird dieses Feature umfassend unterstützt.

Siehe [auch Exemplarische Vorgehensweise: Unterstützung von COM-Interop durch Anzeigen jedes Windows Forms in](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))einem eigenen Thread.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, wie Sie das Formular über einen separaten Thread anzeigen und die <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> -Methode aufrufen, um ein Windows Forms-Nachrichtensystem über diesen Thread zu starten Um diesen Ansatz zu verwenden, müssen Sie jeden Aufruf des Formulars aus der nicht verwalteten Anwendung marshallen, indem Sie die <xref:System.Windows.Forms.Control.Invoke%2A> Methode verwenden.

Dieser Ansatz erfordert, dass jede Instanz eines Formulars über ihren eigenen Thread ausgeführt wird, indem sie ihre eigene Nachrichtenschleife verwendet. Es ist nicht möglich, mehrere Nachrichtenschleifen pro Thread auszuführen. Daher können Sie die Nachrichtenschleife der Clientanwendung nicht ändern. Sie können jedoch die .NET Framework Komponente ändern, um einen neuen Thread zu starten, der seine eigene Nachrichten Schleife verwendet.

[!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]

[!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]

[!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]

## <a name="compile-the-code"></a>Kompilieren des Codes

Kompilieren Sie die Typen `COMForm`, `Form1`und `FormManager` in eine Assembly namens `COMWinform.dll`. Registrieren Sie die Assembly für COM-Interop, indem Sie eine der Methoden verwenden, die unter [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md)beschrieben sind. Sie können die Assembly und deren entsprechende Typbibliotheksdatei (.tlb) in nicht verwalteten Anwendungen verwenden. Beispielsweise können Sie die Typbibliothek als Verweis in einem ausführbaren Visual Basic 6.0-Projekt verwenden.

## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von .NET Framework-Komponenten in COM](../../interop/exposing-dotnet-components-to-com.md)
- [Verpacken einer Assembly für COM](../../interop/packaging-an-assembly-for-com.md)
- [Registrieren von Assemblys bei COM](../../interop/registering-assemblies-with-com.md)
- [Vorgehensweise: Unterstützung von COM-Interop durch Anzeigen eines Windows Forms mit der Show Dialog-Methode](com-interop-by-displaying-a-windows-form-shadow.md)
- [Übersicht über Windows Forms und nicht verwaltete Anwendungen](windows-forms-and-unmanaged-applications-overview.md)
