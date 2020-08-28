---
title: Installieren der GPU-Unterstützung in Model Builder
description: So installieren Sie die GPU-Unterstützung in Model Builder.
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608551"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a>Installieren der GPU-Unterstützung in Model Builder

Hier erfahren Sie, wie Sie die GPU-Treiber installieren, um Ihre GPU mit Model Builder zu verwenden.

## <a name="prerequisites"></a>Voraussetzungen

- Model Builder-Erweiterung für Visual Studio – die Erweiterung ist ab Version 16.6.1 in Visual Studio integriert.
- [Model Builder-Erweiterung für Visual Studio für GPU-Unterstützung](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU)
- Mindestens eine CUDA-kompatible GPU – eine Liste der kompatiblen GPUs finden Sie im [NVIDIA-Leitfaden](https://developer.nvidia.com/cuda-gpus).
- NVIDIA-Entwicklerkonto – Falls Sie nicht über ein Abonnement verfügen, können Sie ein [kostenloses Konto erstellen](https://developer.nvidia.com/developer-program).

## <a name="install-dependencies"></a>Installieren von Abhängigkeiten

1. Installieren Sie [CUDA 10.0](https://developer.nvidia.com/cuda-10.0-download-archive). Stellen Sie sicher, dass Sie CUDA 10.0 installieren – keine neuere Version. Es ist nicht möglich, mehrere Versionen von CUDA zu installieren.
1. Installieren Sie [cuDNN 7.6.4 für CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download). Es ist nicht möglich, mehrere Versionen von cuDNN zu installieren. Laden Sie die ZIP-Datei für cuDNN 7.6.4 herunter, entpacken Sie diese, und kopieren Sie `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` in `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.

## <a name="troubleshooting"></a>Problembehandlung

**Wie finde ich heraus, welche GPU ich habe?**

Befolgen Sie diese Anweisungen:

1. Klicken Sie mit der rechten Maustaste auf den Desktop.
1. Wenn im Kontextmenü „NVIDIA-Systemsteuerung“ oder „NVIDIA-Anzeige“ angezeigt wird, besitzen Sie eine NVIDIA-GPU.
1. Klicken Sie im Kontextmenü auf „NVIDIA-Systemsteuerung“ oder „NVIDIA-Anzeige“.
1. Achten Sie auf die Option „Graphics Card Information“ (Grafikkarte).
1. Dort wird der Name Ihrer NVIDIA-GPU angezeigt.

**Die NVIDIA-Systemsteuerung wird nicht angezeigt oder kann nicht geöffnet werden, obwohl eine NVIDIA-GPU eingebaut ist**

1. Öffnen Sie den Geräte-Manager.
1. Achten Sie auf die Option „Grafikkarten“.
1. Installieren Sie den geeigneten [Treiber](https://www.nvidia.com/drivers) für Ihre GPU.
