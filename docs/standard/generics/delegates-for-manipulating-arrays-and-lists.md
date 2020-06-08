---
title: Generische Delegaten zum Bearbeiten von Arrays und Listen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- delegates [.NET Framework], generic delegates
- chaining delegates
- arrays [.NET Framework], generic delegates
- generic delegates [.NET Framework]
- lists [.NET Framework], generic delegates
- generics [.NET Framework], delegates
ms.assetid: 416be383-cc61-4102-9b1b-88b51adb963e
ms.openlocfilehash: b0ecd8661b7c58645e49ca884ed0499e8c828af9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287531"
---
# <a name="generic-delegates-for-manipulating-arrays-and-lists"></a>Generische Delegaten zum Bearbeiten von Arrays und Listen
Dieses Thema bietet eine Übersicht über generische Delegate für Konvertierungen, Suchprädikate und Aktionen, die für Elemente eines Arrays oder einer Auflistung ausgeführt werden.  
  
## <a name="generic-delegates-for-manipulating-arrays-and-lists"></a>Generische Delegaten zum Bearbeiten von Arrays und Listen  
 Der generische <xref:System.Action%601>-Delegat stellt eine Methode dar, die eine Aktion für ein Element des angegebenen Typs ausführt. Sie können eine Methode erstellen, die die gewünschte Aktion für das Element ausführt, eine Instanz des <xref:System.Action%601>-Delegaten erstellen, die diese Methode darstellt, und dann das Array und den Delegaten an die statische generische <xref:System.Array.ForEach%2A?displayProperty=nameWithType>-Methode übergeben. Die Methode wird für jedes Element des Arrays aufgerufen.  
  
 Die generische <xref:System.Collections.Generic.List%601>-Klasse stellt auch eine <xref:System.Collections.Generic.List%601.ForEach%2A>-Methode bereit, die den <xref:System.Action%601>-Delegaten verwendet. Diese Methode ist nicht generisch.  
  
> [!NOTE]
> Dies stellt einen interessanten Aspekt generischer Typen und Methoden dar. Die <xref:System.Array.ForEach%2A?displayProperty=nameWithType>-Methode muss statisch (`Shared` in Visual Basic) und generisch sein, weil <xref:System.Array> kein generisches Typ ist. Für <xref:System.Array.ForEach%2A?displayProperty=nameWithType> kann nur deshalb ein zu verarbeitender Typ angegeben werden, weil die Methode ihre eigene Typparameterliste hat. Im Gegensatz dazu gehört die nicht generische <xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=nameWithType>-Methode zur generischen Klasse <xref:System.Collections.Generic.List%601> und verwendet daher einfach die Typparameter ihrer Klasse. Die Klasse ist stark typisiert, daher kann es sich bei der Methode um eine Instanzmethode handeln.  
  
 Der generische <xref:System.Predicate%601>-Delegat stellt eine Methode dar, die bestimmt, ob ein bestimmtes Element von Ihnen definierte Kriterien erfüllt. Sie können ihn mit den folgenden statischen generischen Methoden von <xref:System.Array> dazu verwenden, nach einem Element oder einer Reihe von Elementen zu suchen: <xref:System.Array.Exists%2A>, <xref:System.Array.Find%2A>, <xref:System.Array.FindAll%2A>, <xref:System.Array.FindIndex%2A>, <xref:System.Array.FindLast%2A>, <xref:System.Array.FindLastIndex%2A> und <xref:System.Array.TrueForAll%2A>.  
  
 <xref:System.Predicate%601> kann auch mit den entsprechenden nicht generischen Instanzmethoden der generischen <xref:System.Collections.Generic.List%601>-Klasse verwendet werden.  
  
 Der generische <xref:System.Comparison%601>-Delegat ermöglicht es Ihnen, eine Sortierreihenfolge für Array- oder Listenelemente anzugeben, die keine systemeigene Sortierreihenfolge haben, oder die systemeigene Sortierreihenfolge zu überschreiben. Erstellen Sie eine Methode, die den Vergleich ausführt, sowie eine Instanz des <xref:System.Comparison%601>-Delegaten, um die Methode darzustellen, und übergeben Sie dann das Array und den Delegaten an die statische generische Methode <xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29?displayProperty=nameWithType>. Die generische <xref:System.Collections.Generic.List%601>-Klasse stellt eine entsprechende Instanzmethodenüberladung bereit: <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29?displayProperty=nameWithType>.  
  
 Der generische <xref:System.Converter%602>-Delegat ermöglicht es Ihnen, eine Konvertierung zwischen zwei Typen zu definieren und ein Array aus einem Typ in ein Array eines anderen Typs zu konvertieren oder eine Liste eines Typs in eine Liste eines anderen Typs zu konvertieren. Erstellen Sie eine Methode, die die Elemente der vorhandenen Liste in einen neuen Typ konvertiert, erstellen Sie eine Delegatinstanz, die die Methode darstellt, und verwenden Sie die generische statische <xref:System.Array.ConvertAll%2A?displayProperty=nameWithType>-Methode, um ein Array des neuen Typs aus dem ursprünglichen Array zu erstellen, oder die generische <xref:System.Collections.Generic.List%601.ConvertAll%60%601%28System.Converter%7B%600%2C%60%600%7D%29?displayProperty=nameWithType>-Instanzmethode, um eine Liste des neuen Typs aus der ursprünglichen Liste zu erstellen.  
  
### <a name="chaining-delegates"></a>Verketten von Delegaten  
 Viele der Methoden, die diese Delegaten verwenden, geben ein Array oder eine Liste zurück, das oder die an eine andere Methode übergeben werden kann. Wenn Sie beispielsweise bestimmte Elemente eines Arrays auswählen, diese Elemente in einen neuen Typ konvertieren und sie in einem neuen Array speichern möchten, können Sie das Array, das von der generischen <xref:System.Array.FindAll%2A>-Methode zurückgegeben wird, an die generische <xref:System.Array.ConvertAll%2A>-Methode übergeben. Wenn der neue Elementtyp keine natürliche Sortierreihenfolge hat, können Sie das von der generischen der <xref:System.Array.ConvertAll%2A>-Methode zurückgegebene Array an die generische <xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29>-Methode übergeben.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Generics](index.md)
- [Generische Auflistungen in .NET Framework](collections.md)
- [Generische Schnittstellen](interfaces.md)
- [Kovarianz und Kontravarianz](covariance-and-contravariance.md)
