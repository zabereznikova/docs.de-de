---
title: 'Vorgehensweise: Laden und Entladen von Assemblys'
description: Die CLR lädt automatisch .NET-Assemblys, auf die ein Programm verweist. Sie können bestimmte Assemblys auch dynamisch in die aktuelle Anwendungsdomäne laden.
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: e6f1ede055dd3f68bced4eba527b2fc65f7d5715
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378679"
---
# <a name="how-to-load-and-unload-assemblies"></a>Vorgehensweise: Laden und Entladen von Assemblys
Die Assemblys, auf die Ihr Programm verweist, werden automatisch von der CLR (Common Language Runtime) geladen, jedoch ist es auch möglich, spezifische Assemblys dynamisch in die aktuelle Anwendungsdomäne zu laden. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

Im .NET Framework gibt es keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist. In .NET Core verarbeitet die <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType>-Klasse das Entladen von Assemblys. Weitere Informationen finden Sie unter [Verwenden und Debuggen der Entladbarkeit von Assemblys in .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Laden und Entladen von Assemblys

Verwenden Sie eine der vielen Lademethoden, die in den Klassen <xref:System.AppDomain> und <xref:System.Reflection.Assembly> enthalten sind, um eine Assembly in eine Anwendungsdomäne zu laden. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Beachten Sie, dass .NET Core nur eine einzelne Anwendungsdomäne unterstützt.

Zum Entladen einer Assembly im .NET Framework müssen Sie alle Anwendungsdomänen entladen, die sie enthalten. Verwenden Sie die <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>-Methode, um eine Anwendungsdomäne zu entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../framework/app-domains/how-to-unload-an-application-domain.md).

Wenn Sie nur einige Assemblys in einer .NET Framework-Anwendung entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys in .NET](index.md)
- [How to: Laden von Assemblys in eine Anwendungsdomäne](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
