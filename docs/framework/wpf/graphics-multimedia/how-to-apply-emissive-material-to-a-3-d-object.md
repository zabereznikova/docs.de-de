---
title: 'Vorgehensweise: Anwenden von Emissive Material auf ein 3D-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: b898148fa07950e3ad1eddcaf9206f7d6a837241
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698967"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a>Vorgehensweise: Anwenden von Emissive Material auf ein 3D-Objekt
Das folgende Beispiel zeigt, wie Sie mit <xref:System.Windows.Media.Media3D.EmissiveMaterial> zu einem bestehenden Material auf die Farbe des Pinsels von EmissiveMaterial Farbe hinzuzufügen. Der folgende Code zeigt <xref:System.Windows.Media.Media3D.DiffuseMaterial> und <xref:System.Windows.Media.Media3D.EmissiveMaterial> in Blau hinzuzufügen, zu der DiffuseMaterial Darstellung angewendet.  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 In prozeduralem Code:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel, in XAML.  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden wird das gesamte Beispiel in prozeduralem Code ein.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Animieren von Material-Eigenschaften in einer 3D-Szene](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
