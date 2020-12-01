---
title: Reflektion in .NET Framework für Windows Store-Apps
description: Verwenden von Reflexion in .NET für Windows Store-Apps Es gibt eine Reihe von Reflexionstypen und -membern, die in Windows Store-Apps verwendet werden können und für alle .NET Framework-Versionen verfügbar sind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
ms.openlocfilehash: dd92696fdbe534c549b3aba25533533280485cfe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263411"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflektion in .NET Framework für Windows Store-Apps

Ab .NET Framework 4.5 stellt das .NET Framework eine Reihe von Reflexionstypen und -membern für Windows 8.x Store-Apps zur Verfügung. Diese Typen und Member sind im vollständigen .NET Framework sowie in .NET für Windows Store-Apps verfügbar. In diesem Dokument werden die Hauptunterschiede zwischen ihnen und ihren Entsprechungen in .NET Framework 4 und früheren Versionen erklärt.  
  
 Wenn Sie eine Windows 8.x Store-App erstellen, müssen Sie die Reflexionstypen und -member in .NET für Windows 8.x Store-Apps verwenden. Diese Typen und Member sind ebenfalls für die Verwendung in Desktop-Apps verfügbar, jedoch nicht erforderlich, sodass Sie denselben Code für beide Typen von Apps verwenden können.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo und Laden von Assemblys  

 In .NET für Windows 8.x Store-Apps enthält die Klasse <xref:System.Reflection.TypeInfo> einen Teil der Funktionen der Klasse <xref:System.Type> von .NET Framework 4. Ein <xref:System.Type>-Objekt stellt einen Verweis auf eine Typdefinition dar, während ein <xref:System.Reflection.TypeInfo>-Objekt die Typdefinition selbst darstellt. Dadurch können Sie <xref:System.Type>-Objekte ändern, ohne dass die Laufzeit unbedingt die Assembly laden muss, auf die sie verweisen. Das Abrufen des zugeordneten <xref:System.Reflection.TypeInfo>-Objekts erzwingt das Laden der Assembly.  
  
 <xref:System.Reflection.TypeInfo> enthält viele der Member, die in <xref:System.Type> verfügbar sind, und viele der Reflexionseigenschaften in .NET für Windows 8.x Store-Apps geben Auflistungen von <xref:System.Reflection.TypeInfo>-Objekten zurück. Um ein <xref:System.Reflection.TypeInfo>-Objekt aus einem <xref:System.Type>-Objekt abzurufen, verwenden Sie die <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>-Methode.  
  
## <a name="query-methods"></a>Abfragemethoden  

 Verwenden Sie in .NET für Windows 8.x Store-Apps die Reflexionseigenschaften, die <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen zurückgeben, anstelle von Methoden, die Arrays zurückgeben. Reflektionskontexte können einen verzögerten Durchlauf dieser Auflistungen für große Assemblys oder Typen implementieren.  
  
 Die Reflektionseigenschaften geben nur die deklarierten Methoden für ein bestimmtes Objekt wieder. Sie durchlaufen nicht die Vererbungsstruktur. Darüber hinaus verwenden sie keine <xref:System.Reflection.BindingFlags>-Parameter zum Filtern. Stattdessen wird das Filtern im Benutzercode ausgeführt, indem LINQ-Abfragen für die zurückgegebenen Auflistungen verwendet werden. Für Reflektionsobjekte, die mit der Laufzeit ausgelöst werden (z. B. als Ergebnis von `typeof(Object)`), wird das Durchlaufen der Vererbungsstruktur am besten erreicht, indem die Hilfsmethoden der <xref:System.Reflection.RuntimeReflectionExtensions>-Klasse verwendet werden. Consumer von Objekten benutzerdefinierter Reflektionskontexte können diese Methoden nicht verwenden und müssen selbst die Vererbungsstruktur durchlaufen.  
  
## <a name="restrictions"></a>Beschränkungen  

 In einer Windows 8.x Store-App wird der Zugriff auf einige .NET Framework-Typen und -Member eingeschränkt. Sie können beispielsweise .NET Framework-Methoden, die nicht in .NET für Windows 8.x Store-Apps enthalten sind, nicht mit einem <xref:System.Reflection.MethodInfo>-Objekt aufrufen. Darüber hinaus werden bestimmte Typen und Member, die innerhalb einer Windows 8.x Store-App als nicht sicher eingestuft werden, sowie <xref:System.Runtime.InteropServices.Marshal>- und <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal>-Member blockiert. Diese Einschränkung betrifft nur .NET Framework-Typen und -Member. Sie können Ihren Code oder Code von Drittanbietern wie gewohnt aufrufen.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel werden die Reflexionstypen und -member in .NET für Windows 8.x Store-Apps verwendet, um die Methoden und Eigenschaften des <xref:System.Globalization.Calendar>-Typs abzurufen, einschließlich geerbter Methoden und Eigenschaften. Zum Ausführen dieses Codes fügen Sie ihn in eine Codedatei für eine Windows 8.x Store-Seite ein, die ein Steuerelement <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> mit dem Namen `textblock1` in einem Projekt namens „Reflection“ (Reflexion) enthält. Wenn Sie diesen Code in einem Projekt mit einem anderen Namen einfügen, müssen Sie darauf achten, dass Sie den Namespacenamen entsprechend Ihrem Projekt ändern.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Reflexion](reflection.md)
