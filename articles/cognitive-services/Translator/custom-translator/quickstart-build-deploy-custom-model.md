---
title: "Quickstart: Build, deploy, and use a custom model"
titleSuffix: Azure Cognitive Services
description: A step-by-step guide to building a translation system using the Custom Translator Legacy.
author: laujan
manager: nitinme
ms.service: cognitive-services
ms.subservice: translator-text
ms.date: 12/06/2021
ms.author: lajanuar
ms.topic: quickstart
ms.custom: mode-other
#Customer intent: As a user, I want to understand how to use Custom Translator so that I can build, deploy, and use a custom model for translation.
---
# Quickstart: Build, deploy, and use a custom model for translation

This article provides step-by-step instructions to build a translation system with Custom Translator.

## Prerequisites

1. To use the [Custom Translator](https://portal.customtranslator.azure.ai)
    Portal, you will need a [Microsoft account](https://signup.live.com) or [Azure AD account](../../../active-directory/fundamentals/active-directory-whatis.md)
    (organization account hosted on Azure) to sign in.

2. A subscription to the Translator Text API via the Azure portal. You will need the Translator Text API subscription key to associate with your workspace in Custom Translator. See [how to sign up for the Translator Text API](../translator-how-to-signup.md).

3. When you have both of the above, sign in to the
    [Custom Translator](https://portal.customtranslator.azure.ai) portal to create workspaces, projects, upload files and create/deploy models.

You can read an overview of translation and custom translation, learn some tips, and watch a getting started video in the [Azure AI technical blog](https://techcommunity.microsoft.com/t5/azure-ai/customize-a-translation-to-make-sense-in-a-specific-context/ba-p/2811956). 

You can also view a full, start to finish walkthrough video of Custom Translator on [YouTube](https://www.youtube.com/watch?v=TykB6WDTkRc&t=3s).

>[!Note]
>Custom Translator does not support creating workspace for Translator Text API resource that was created inside [Enabled VNET](../../../api-management/api-management-using-with-vnet.md).

## Create a workspace

If you are first-time user, you will be asked to agree to the Terms of Service to create a workspace associated with your Microsoft Translator Text API subscription.

![Create workspace](media/quickstart/terms-of-service.png)
![Create workspace image 1](media/quickstart/create-workspace-1.png)
![Create workspace image 2](media/quickstart/create-workspace-2.png)
![Create workspace image 3](media/quickstart/create-workspace-3.png)
![Create workspace image 4](media/quickstart/create-workspace-4.png)
![Create workspace image 5](media/quickstart/create-workspace-5.png)
![Create workspace image 6](media/quickstart/create-workspace-6.png)

On subsequent visits to the Custom Translator portal, navigate to the Settings page where you can manage your workspace, create more workspaces, associate your Microsoft Translator Text API subscription key with your workspaces, add co-owners, and change a subscription key.

## Create a project

On the Custom Translator portal landing page, select **New Project**. On the dialog you can enter your desired project name, language pair, category, and other relevant field information. Then, save
your project. For more details, visit [Create Project](how-to-create-project.md).

![Create project](media/how-to/how-to-create-project.png)


## Upload documents

Next, upload [training](training-and-model.md#training-document-type-for-custom-translator), [tuning](training-and-model.md#tuning-document-type-for-custom-translator) and [testing](training-and-model.md#testing-dataset-for-custom-translator) document sets. You can upload both [parallel](what-are-parallel-documents.md) and combo documents. You can also upload [dictionary](what-is-dictionary.md).

You can upload documents from either the documents tab or from a specific
project's page.

![Upload documents](media/how-to/how-to-upload-1.png)

When uploading documents, choose the document type (training, tuning, or
testing), and the language pair. When uploading parallel documents, you'll need
to additionally specify a document name. For more details, visit [Upload document](how-to-upload-document.md).

## Create a model

When all your required documents are uploaded, the next step is to build your model.

Select the project you've created. You'll see all the documents you've uploaded
that share a language pair with this project. Select the documents that you want
included in your model. You can select [training](training-and-model.md#training-document-type-for-custom-translator),
[tuning](training-and-model.md#tuning-document-type-for-custom-translator), and [testing](training-and-model.md#testing-dataset-for-custom-translator) data or select just
training data and let Custom Translator automatically build tuning and test sets
for your model.

![Create a model](media/how-to/how-to-train-model-1.png)

When you've finished selecting your desired documents, select the **Create Model** button to
create your model and start training. You can see the status of your training,
and details for all the models you've trained, in the Models tab.

For more details, visit [Create a Model](how-to-train-model.md).

## Analyze your model

Once your training has completed successfully, inspect the results. The BLEU
score is one metric that indicates the quality of your translation. You can also
manually compare the translations made with your custom model to the
translations provided in your test set by navigating to the **Test** tab and selecting **System Results**. Manually inspecting a few of these translations will give you a good idea of the quality of translation produced by your system. For more details, visit [System Test Results](how-to-view-system-test-results.md).

## Deploy a trained model

When you are ready to deploy your trained model, select the **Deploy** button. You can have one deployed model per project, and you can view the status of your deployment in the Status column. For more details, visit [Model Deployment](how-to-view-system-test-results.md#deploy-a-model)

![Deploy a trained model](media/how-to/how-to-deploy.png)

## Swap deployed model

To swap a deployed model with another within a project, select the **Swap** button displayed next to the desired model. During the swap process, the deployed model will continue to be available to serve translation requests.

![Swap deployed model](media/how-to/how-to-swap-model.png)

## Use a deployed model

Deployed models can be accessed via the Microsoft Translator [Text API V3 by
specifying the CategoryID](../reference/v3-0-translate.md?tabs=curl). More information about the Translator Text API can
be found on the [API
Reference](../reference/v3-0-reference.md) webpage.

## Next steps

- Learn how to navigate the [Custom Translator workspace and manage your projects](workspace-and-project.md).
