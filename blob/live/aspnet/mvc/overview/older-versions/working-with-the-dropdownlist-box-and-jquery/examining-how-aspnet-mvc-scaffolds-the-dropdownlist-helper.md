---
uid: mvc/overview/older-versions/working-with-the-dropdownlist-box-and-jquery/examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper
title: Examinar como o ASP.NET MVC scaffolds o auxiliar DropDownList | Microsoft Docs
author: Rick-Anderson
description: 
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/12/2012
ms.topic: article
ms.assetid: 8921d7f2-21f0-427a-8b27-2df7251174b0
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions/working-with-the-dropdownlist-box-and-jquery/examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper
msc.type: authoredcontent
ms.openlocfilehash: b5210f9a29f82fbadd0e6dd2d81bd85e7f23ae7e
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="examining--how--aspnet-mvc-scaffolds-the-dropdownlist-helper"></a><span data-ttu-id="494e0-102">Examinar como o ASP.NET MVC scaffolds o auxiliar DropDownList</span><span class="sxs-lookup"><span data-stu-id="494e0-102">Examining  how  ASP.NET MVC scaffolds the DropDownList Helper</span></span>
====================
<span data-ttu-id="494e0-103">Por [Rick Anderson](https://github.com/Rick-Anderson)</span><span class="sxs-lookup"><span data-stu-id="494e0-103">by [Rick Anderson](https://github.com/Rick-Anderson)</span></span>

<span data-ttu-id="494e0-104">Em **Solution Explorer**, com o botão direito do *controladores* pasta e, em seguida, selecione **Adicionar controlador**.</span><span class="sxs-lookup"><span data-stu-id="494e0-104">In **Solution Explorer**, right-click the *Controllers* folder and then select **Add Controller**.</span></span> <span data-ttu-id="494e0-105">Nome do controlador **StoreManagerController**.</span><span class="sxs-lookup"><span data-stu-id="494e0-105">Name the controller **StoreManagerController**.</span></span> <span data-ttu-id="494e0-106">Definir as opções para o **Adicionar controlador** diálogo conforme mostrado na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-106">Set the options for the **Add Controller** dialog as shown in the image below.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image1.png)

<span data-ttu-id="494e0-107">Editar o *StoreManager\Index.cshtml* exibir e remover `AlbumArtUrl`.</span><span class="sxs-lookup"><span data-stu-id="494e0-107">Edit the *StoreManager\Index.cshtml* view and remove `AlbumArtUrl`.</span></span> <span data-ttu-id="494e0-108">Removendo `AlbumArtUrl` tornar a apresentação mais legível.</span><span class="sxs-lookup"><span data-stu-id="494e0-108">Removing `AlbumArtUrl` will make the presentation more readable.</span></span> <span data-ttu-id="494e0-109">O código completo é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-109">The completed code is shown below.</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample1.cshtml)]

<span data-ttu-id="494e0-110">Abra o *Controllers\StoreManagerController.cs* de arquivos e localizar o `Index` método.</span><span class="sxs-lookup"><span data-stu-id="494e0-110">Open the *Controllers\StoreManagerController.cs* file and find the `Index` method.</span></span> <span data-ttu-id="494e0-111">Adicionar o `OrderBy` cláusula para álbuns serão classificados pelo preço.</span><span class="sxs-lookup"><span data-stu-id="494e0-111">Add the `OrderBy` clause so the albums will be sorted by price.</span></span> <span data-ttu-id="494e0-112">O código completo é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-112">The complete code is shown below.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample2.cs)]

<span data-ttu-id="494e0-113">A classificação por preço tornará mais fácil de testar as alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="494e0-113">Sorting by price will make it easier to test changes to the database.</span></span> <span data-ttu-id="494e0-114">Quando você estiver testando o editar e cria métodos, você pode usar um baixo preço para que os dados salvos aparecerão primeiro.</span><span class="sxs-lookup"><span data-stu-id="494e0-114">When you are testing the edit and create methods, you can use a low price so the saved data will appear first.</span></span>

<span data-ttu-id="494e0-115">Abra o *StoreManager\Edit.cshtml* arquivo.</span><span class="sxs-lookup"><span data-stu-id="494e0-115">Open the *StoreManager\Edit.cshtml* file.</span></span> <span data-ttu-id="494e0-116">Adicione a linha a seguir logo após a marca de legenda.</span><span class="sxs-lookup"><span data-stu-id="494e0-116">Add the following line just after the legend tag.</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample3.cshtml)]

<span data-ttu-id="494e0-117">O código a seguir mostra o contexto dessa alteração:</span><span class="sxs-lookup"><span data-stu-id="494e0-117">The following code shows the context of this change:</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample4.cshtml)]

<span data-ttu-id="494e0-118">O `AlbumId` é necessária para fazer alterações em um registro de álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-118">The `AlbumId` is required to make changes to an album record.</span></span>

<span data-ttu-id="494e0-119">Pressione CTRL+F5 para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="494e0-119">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="494e0-120">Selecione esta opção para o **Admin** link e, em seguida, selecione o **criar novo** link para criar um novo álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-120">Select to the **Admin** link, then select the **Create New** link to create a new album.</span></span> <span data-ttu-id="494e0-121">Verifique se que as informações de álbum foi salvo.</span><span class="sxs-lookup"><span data-stu-id="494e0-121">Verify the album information was saved.</span></span> <span data-ttu-id="494e0-122">Editar um álbum e verifique se as alterações feitas são persistentes.</span><span class="sxs-lookup"><span data-stu-id="494e0-122">Edit an album and verify the changes you made are persisted.</span></span>

### <a name="the-album-schema"></a><span data-ttu-id="494e0-123">O esquema de álbum</span><span class="sxs-lookup"><span data-stu-id="494e0-123">The Album Schema</span></span>

<span data-ttu-id="494e0-124">O `StoreManager` controlador criado pelo mecanismo de scaffolding MVC permite acesso CRUD (criar, ler, atualizar, excluir) em álbuns no banco de dados de repositório de música.</span><span class="sxs-lookup"><span data-stu-id="494e0-124">The `StoreManager` controller created by the MVC scaffolding mechanism allows CRUD (Create, Read, Update, Delete) access to the albums in the music store database.</span></span> <span data-ttu-id="494e0-125">O esquema para obter informações de álbum é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="494e0-125">The schema for album information is shown below:</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image2.png)

<span data-ttu-id="494e0-126">O `Albums` tabela não armazena o gênero álbum e a descrição, ele armazena uma chave estrangeira para a `Genres` tabela.</span><span class="sxs-lookup"><span data-stu-id="494e0-126">The `Albums` table does not store the album genre and description, it stores a foreign key to the `Genres` table.</span></span> <span data-ttu-id="494e0-127">O `Genres` tabela contém o nome de gênero e descrição.</span><span class="sxs-lookup"><span data-stu-id="494e0-127">The `Genres` table contains the genre name and description.</span></span> <span data-ttu-id="494e0-128">Da mesma forma, o `Albums` tabela não contém o nome do álbum artistas, mas uma chave estrangeira para a `Artists` tabela.</span><span class="sxs-lookup"><span data-stu-id="494e0-128">Likewise, the `Albums` table doesn't contain the album artists name, but a foreign key to the `Artists` table.</span></span> <span data-ttu-id="494e0-129">O `Artists` tabela contém o nome do artista.</span><span class="sxs-lookup"><span data-stu-id="494e0-129">The `Artists` table contains the artist's name.</span></span> <span data-ttu-id="494e0-130">Se você examinar os dados de `Albums` tabela, você pode ver cada linha contém uma chave estrangeira para a `Genres` tabela e uma chave estrangeira para a `Artists` tabela.</span><span class="sxs-lookup"><span data-stu-id="494e0-130">If you examine the data in the `Albums` table, you can see each row contains a foreign key to the `Genres` table and a foreign key to the `Artists` table.</span></span> <span data-ttu-id="494e0-131">A imagem a seguir mostram alguns dados da tabela de `Albums` tabela.</span><span class="sxs-lookup"><span data-stu-id="494e0-131">The image below show some table data from the `Albums` table.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image3.png)

### <a name="the-html-select-tag"></a><span data-ttu-id="494e0-132">A marca de seleção HTML</span><span class="sxs-lookup"><span data-stu-id="494e0-132">The HTML Select Tag</span></span>

<span data-ttu-id="494e0-133">O HTML `<select>` elemento (criado pelo HTML [DropDownList](https://msdn.microsoft.com/en-us/library/dd492948.aspx) auxiliar) é usado para exibir uma lista completa de valores (como a lista de gêneros).</span><span class="sxs-lookup"><span data-stu-id="494e0-133">The HTML `<select>` element (created by the HTML [DropDownList](https://msdn.microsoft.com/en-us/library/dd492948.aspx) helper) is used to display a complete list of values (such as the list of genres).</span></span> <span data-ttu-id="494e0-134">Para editar formulários, quando o valor atual é conhecido, a lista de seleção pode exibir o valor atual.</span><span class="sxs-lookup"><span data-stu-id="494e0-134">For edit forms, when the current value is known, the select list can display the current value.</span></span> <span data-ttu-id="494e0-135">Vimos anteriormente nesse quando definimos o valor selecionado **comédia**.</span><span class="sxs-lookup"><span data-stu-id="494e0-135">We saw this previously when we set the selected value to **Comedy**.</span></span> <span data-ttu-id="494e0-136">A lista de seleção é ideal para a exibição de categoria ou dados de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="494e0-136">The select list is ideal for displaying category or foreign key data.</span></span> <span data-ttu-id="494e0-137">O `<select>` elemento para a chave estrangeira gênero exibe a lista de nomes de gênero possíveis, mas quando você salvar o formulário a propriedade de gênero é atualizada com o gênero valor de chave estrangeira, não o nome exibido gênero.</span><span class="sxs-lookup"><span data-stu-id="494e0-137">The `<select>` element for the Genre foreign key displays the list of possible genre names, but when you save the form the Genre property is updated with the Genre foreign key value, not the displayed genre name.</span></span> <span data-ttu-id="494e0-138">Na imagem abaixo, o gênero selecionado é **Disco** e artista **Donna Summer**.</span><span class="sxs-lookup"><span data-stu-id="494e0-138">In the image below, the genre selected is **Disco** and the artist is **Donna Summer**.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image4.png)

### <a name="examining-the-aspnet-mvc-scaffolded-code"></a><span data-ttu-id="494e0-139">Examinar o ASP.NET MVC Scaffold código</span><span class="sxs-lookup"><span data-stu-id="494e0-139">Examining the ASP.NET MVC Scaffolded Code</span></span>

<span data-ttu-id="494e0-140">Abra o *Controllers\StoreManagerController.cs* de arquivos e localizar o `HTTP GET Create` método.</span><span class="sxs-lookup"><span data-stu-id="494e0-140">Open the *Controllers\StoreManagerController.cs* file and find the `HTTP GET Create` method.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample5.cs)]

<span data-ttu-id="494e0-141">O `Create` método adiciona dois [SelectList](https://msdn.microsoft.com/en-us/library/system.web.mvc.selectlist.aspx) objetos para o `ViewBag`, uma para conter as informações de gênero e outra para conter as informações de artista.</span><span class="sxs-lookup"><span data-stu-id="494e0-141">The `Create` method adds two [SelectList](https://msdn.microsoft.com/en-us/library/system.web.mvc.selectlist.aspx) objects to the `ViewBag`, one to contain the genre information, and one to contain the artist information.</span></span> <span data-ttu-id="494e0-142">O [SelectList](https://msdn.microsoft.com/en-us/library/dd505286.aspx) sobrecarga de construtor usada acima usa três argumentos:</span><span class="sxs-lookup"><span data-stu-id="494e0-142">The [SelectList](https://msdn.microsoft.com/en-us/library/dd505286.aspx) constructor overload used above takes three arguments:</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample6.cs)]

1. <span data-ttu-id="494e0-143">*itens*: um [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable.aspx) contendo os itens na lista.</span><span class="sxs-lookup"><span data-stu-id="494e0-143">*items*: An [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable.aspx) containing the items in the list.</span></span> <span data-ttu-id="494e0-144">No exemplo acima, a lista de gêneros retornado por `db.Genres`.</span><span class="sxs-lookup"><span data-stu-id="494e0-144">In the example above, the list of genres returned by `db.Genres`.</span></span>
2. <span data-ttu-id="494e0-145">*dataValueField*: O nome da propriedade no **IEnumerable** lista que contém o valor da chave.</span><span class="sxs-lookup"><span data-stu-id="494e0-145">*dataValueField*: The name of the property in the **IEnumerable** list that contains the key value.</span></span> <span data-ttu-id="494e0-146">No exemplo acima, `GenreId` e `ArtistId`.</span><span class="sxs-lookup"><span data-stu-id="494e0-146">In the example above, `GenreId` and `ArtistId`.</span></span>
3. <span data-ttu-id="494e0-147">*dataTextField*: O nome da propriedade no **IEnumerable** lista que contém as informações a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="494e0-147">*dataTextField*: The name of the property in the **IEnumerable** list that contains the information to display.</span></span> <span data-ttu-id="494e0-148">No artistas e tabela de gênero, o `name` campo será usado.</span><span class="sxs-lookup"><span data-stu-id="494e0-148">In both the artists and genre table, the `name` field is used.</span></span>

<span data-ttu-id="494e0-149">Abra o *Views\StoreManager\Create.cshtml* de arquivo e examine o `Html.DropDownList` marcação de auxiliar para o campo de gênero.</span><span class="sxs-lookup"><span data-stu-id="494e0-149">Open the *Views\StoreManager\Create.cshtml* file and examine the `Html.DropDownList` helper markup for the genre field.</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample7.cshtml)]

<span data-ttu-id="494e0-150">A primeira linha mostra que usa o modo de exibição de criar um `Album` modelo.</span><span class="sxs-lookup"><span data-stu-id="494e0-150">The first line shows that the create view takes an `Album` model.</span></span> <span data-ttu-id="494e0-151">No `Create` método mostrado acima, nenhum modelo foi passado, para o modo de exibição obtém uma **nulo** `Album` modelo.</span><span class="sxs-lookup"><span data-stu-id="494e0-151">In the `Create` method shown above, no model was passed, so the view gets a **null** `Album` model.</span></span> <span data-ttu-id="494e0-152">Neste momento, estamos criando um novo álbum para que não temos nenhum `Album` dados para ele.</span><span class="sxs-lookup"><span data-stu-id="494e0-152">At this point we are creating a new album so we don't have any `Album` data for it.</span></span>

<span data-ttu-id="494e0-153">O [Html.DropDownList](https://msdn.microsoft.com/en-us/library/dd492948.aspx) sobrecarga mostrada acima obtém o nome do campo para associar ao modelo.</span><span class="sxs-lookup"><span data-stu-id="494e0-153">The [Html.DropDownList](https://msdn.microsoft.com/en-us/library/dd492948.aspx) overload shown above takes the name of the field to bind to the model.</span></span> <span data-ttu-id="494e0-154">Ele também usa esse nome para procurar um **ViewBag** objeto contendo um [SelectList](https://msdn.microsoft.com/en-us/library/dd505286.aspx) objeto.</span><span class="sxs-lookup"><span data-stu-id="494e0-154">It also uses this name to look for a **ViewBag** object containing a [SelectList](https://msdn.microsoft.com/en-us/library/dd505286.aspx) object.</span></span> <span data-ttu-id="494e0-155">Usando essa sobrecarga, é necessário o nome de **ViewBag SelectList** objeto `GenreId`.</span><span class="sxs-lookup"><span data-stu-id="494e0-155">Using this overload, you are required to name the **ViewBag SelectList** object `GenreId`.</span></span> <span data-ttu-id="494e0-156">O segundo parâmetro (`String.Empty`) é o texto a ser exibido quando nenhum item selecionado.</span><span class="sxs-lookup"><span data-stu-id="494e0-156">The second parameter (`String.Empty`) is the text to display when no item is selected.</span></span> <span data-ttu-id="494e0-157">Isso é exatamente o que queremos ao criar um novo álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-157">This is exactly what we want when creating a new album.</span></span> <span data-ttu-id="494e0-158">Se você remover o segundo parâmetro e usou o código a seguir:</span><span class="sxs-lookup"><span data-stu-id="494e0-158">If you removed the second parameter and used the following code:</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample8.cshtml)]

<span data-ttu-id="494e0-159">A lista de seleção padrão para o primeiro elemento ou Rock em nosso exemplo.</span><span class="sxs-lookup"><span data-stu-id="494e0-159">The select list would default to the first element, or Rock in our sample.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image5.png)

<span data-ttu-id="494e0-160">Examinando o `HTTP POST Create` método.</span><span class="sxs-lookup"><span data-stu-id="494e0-160">Examining the `HTTP POST Create` method.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample9.cs)]

<span data-ttu-id="494e0-161">Esta sobrecarga do `Create` leva um `album` objeto, criado pelo sistema de associação do ASP.NET MVC modelo entre os valores de formulário postado.</span><span class="sxs-lookup"><span data-stu-id="494e0-161">This overload of the `Create` method takes an `album` object, created by the ASP.NET MVC model binding system from the form values posted.</span></span> <span data-ttu-id="494e0-162">Quando você envia um novo álbum, se o estado do modelo é válido e não há erros de banco de dados, o novo álbum é adicionado o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="494e0-162">When you submit a new album, if model state is valid and there are no database errors, the new album is added the database.</span></span> <span data-ttu-id="494e0-163">A imagem a seguir mostra a criação de um novo álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-163">The following image shows the creation of a new album.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image6.png)

<span data-ttu-id="494e0-164">Você pode usar o [ferramenta fiddler](http://www.fiddler2.com/fiddler2/) para examinar os valores de formulário postado essa associação de modelo do ASP.NET MVC usa para criar o objeto álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-164">You can use the [fiddler tool](http://www.fiddler2.com/fiddler2/) to examine the posted form values that ASP.NET MVC model binding uses to create the album object.</span></span>

<span data-ttu-id="494e0-165">![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image7.png).</span><span class="sxs-lookup"><span data-stu-id="494e0-165">![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image7.png).</span></span>

### <a name="refactoring-the-viewbag-selectlist-creation"></a><span data-ttu-id="494e0-166">A criação de ViewBag SelectList de refatoração</span><span class="sxs-lookup"><span data-stu-id="494e0-166">Refactoring the ViewBag SelectList Creation</span></span>

<span data-ttu-id="494e0-167">Ambos os o `Edit` métodos e `HTTP POST Create` método tem código idêntico para configurar o **SelectList** no **ViewBag**.</span><span class="sxs-lookup"><span data-stu-id="494e0-167">Both the `Edit` methods and the `HTTP POST Create` method have identical code to set up the **SelectList** in the **ViewBag**.</span></span> <span data-ttu-id="494e0-168">No espírito do [SECA](http://en.wikipedia.org/wiki/Don't_repeat_yourself), podemos refatorar o esse código.</span><span class="sxs-lookup"><span data-stu-id="494e0-168">In the spirit of [DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself), we will refactor this code.</span></span> <span data-ttu-id="494e0-169">Verifique o uso deste refatorado código mais tarde.</span><span class="sxs-lookup"><span data-stu-id="494e0-169">We'll make use of this refactored code later.</span></span>

<span data-ttu-id="494e0-170">Criar um novo método para adicionar um gênero e artista **SelectList** para o **ViewBag**.</span><span class="sxs-lookup"><span data-stu-id="494e0-170">Create a new method to add a genre and artist **SelectList** to the **ViewBag**.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample10.cs)]

<span data-ttu-id="494e0-171">Substitua as duas linhas definindo o `ViewBag` em cada uma da `Create` e `Edit` métodos com uma chamada para o `SetGenreArtistViewBag` método.</span><span class="sxs-lookup"><span data-stu-id="494e0-171">Replace the two lines setting the `ViewBag` in each of the `Create` and `Edit` methods with a call to the `SetGenreArtistViewBag` method.</span></span> <span data-ttu-id="494e0-172">O código completo é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-172">The completed code is shown below.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample11.cs)]

<span data-ttu-id="494e0-173">Criar um novo álbum e editar um álbum para verificar que as alterações estão funcionando.</span><span class="sxs-lookup"><span data-stu-id="494e0-173">Create a new album and edit an album to verify the changes work.</span></span>

### <a name="explicitly-passing-the-selectlist-to-the-dropdownlist"></a><span data-ttu-id="494e0-174">Explicitamente passando o SelectList para DropDownList</span><span class="sxs-lookup"><span data-stu-id="494e0-174">Explicitly Passing the SelectList to the DropDownList</span></span>

<span data-ttu-id="494e0-175">As exibições de criar e editar criadas com o uso do ASP.NET MVC scaffolding seguintes **DropDownList** sobrecarga:</span><span class="sxs-lookup"><span data-stu-id="494e0-175">The create and edit views created by the ASP.NET MVC scaffolding use the following **DropDownList** overload:</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample12.cs)]

<span data-ttu-id="494e0-176">O `DropDownList` marcação para o modo de exibição de criação é mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-176">The `DropDownList` markup for the create view is shown below.</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample13.cshtml)]

<span data-ttu-id="494e0-177">Porque o `ViewBag` propriedade para o `SelectList` chamado `GenreId`, o **DropDownList** usará o `GenreId` **SelectList** no **ViewBag** .</span><span class="sxs-lookup"><span data-stu-id="494e0-177">Because the `ViewBag` property for the `SelectList` is named `GenreId`, the **DropDownList** helper will use the `GenreId`**SelectList** in the **ViewBag**.</span></span> <span data-ttu-id="494e0-178">A seguir **DropDownList** sobrecarga, o `SelectList` é passado explicitamente.</span><span class="sxs-lookup"><span data-stu-id="494e0-178">In the following **DropDownList** overload, the `SelectList` is explicitly passed in.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample14.cs)]

<span data-ttu-id="494e0-179">Abra o *Views\StoreManager\Edit.cshtml* de arquivo e altere o **DropDownList** chamada explicitamente passe a **SelectList**, usando a sobrecarga acima.</span><span class="sxs-lookup"><span data-stu-id="494e0-179">Open the *Views\StoreManager\Edit.cshtml* file, and change the **DropDownList** call to explicitly pass in the **SelectList**, using the overload above.</span></span> <span data-ttu-id="494e0-180">Faça isso para a categoria de gênero.</span><span class="sxs-lookup"><span data-stu-id="494e0-180">Do this for the Genre category.</span></span> <span data-ttu-id="494e0-181">O código completo é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="494e0-181">The completed code is shown below:</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample15.cshtml)]

<span data-ttu-id="494e0-182">Execute o aplicativo e clique no **Admin** link, em seguida, navegue até um álbum Jazz e selecione o **editar** link.</span><span class="sxs-lookup"><span data-stu-id="494e0-182">Run the application and click the **Admin** link, then navigate to a Jazz album and select the **Edit** link.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image8.png)

<span data-ttu-id="494e0-183">Em vez de Mostrar Jazz como o gênero selecionado no momento, Rock é exibida.</span><span class="sxs-lookup"><span data-stu-id="494e0-183">Instead of showing Jazz as the currently selected genre, Rock is displayed.</span></span> <span data-ttu-id="494e0-184">Quando o argumento de cadeia de caracteres (a propriedade para associar) e o **SelectList** objeto têm o mesmo nome, o valor selecionado não é usado.</span><span class="sxs-lookup"><span data-stu-id="494e0-184">When the string argument (the property to bind) and the **SelectList** object have the same name, the selected value is not used.</span></span> <span data-ttu-id="494e0-185">Quando não houver nenhum valor selecionado fornecido, os navegadores padrão para o primeiro elemento no **SelectList**(que é **Rock** no exemplo acima).</span><span class="sxs-lookup"><span data-stu-id="494e0-185">When there is no selected value provided, browsers default to the first element in the **SelectList**(which is **Rock** in the example above).</span></span> <span data-ttu-id="494e0-186">Essa é uma limitação conhecida do **DropDownList** auxiliar.</span><span class="sxs-lookup"><span data-stu-id="494e0-186">This is a known limitation of the **DropDownList** helper.</span></span>

<span data-ttu-id="494e0-187">Abra o *Controllers\StoreManagerController.cs* de arquivo e altere o **SelectList** para os nomes de objeto `Genres` e `Artists`.</span><span class="sxs-lookup"><span data-stu-id="494e0-187">Open the *Controllers\StoreManagerController.cs* file and change the **SelectList** object names to `Genres` and `Artists`.</span></span> <span data-ttu-id="494e0-188">O código completo é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="494e0-188">The completed code is shown below:</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample16.cs)]

<span data-ttu-id="494e0-189">Os nomes de artistas e gêneros são melhor nomes para as categorias, pois eles contêm mais do que apenas a ID de cada categoria.</span><span class="sxs-lookup"><span data-stu-id="494e0-189">The names Genres and Artists are better names for the categories, as they contain more than just the ID of each category.</span></span> <span data-ttu-id="494e0-190">A refatoração que foi anteriormente paga.</span><span class="sxs-lookup"><span data-stu-id="494e0-190">The refactoring we did earlier paid off.</span></span> <span data-ttu-id="494e0-191">Em vez de alterar o **ViewBag** em quatro métodos, nossas alterações sejam isoladas de `SetGenreArtistViewBag` método.</span><span class="sxs-lookup"><span data-stu-id="494e0-191">Instead of changing the **ViewBag** in four methods, our changes were isolated to the `SetGenreArtistViewBag` method.</span></span>

<span data-ttu-id="494e0-192">Alterar o **DropDownList** chamar a criar e editar modos de exibição para usar o novo **SelectList** nomes.</span><span class="sxs-lookup"><span data-stu-id="494e0-192">Change the **DropDownList** call in the create and edit views to use the new **SelectList** names.</span></span> <span data-ttu-id="494e0-193">A marcação de novo para o modo de exibição de edição é mostrada abaixo:</span><span class="sxs-lookup"><span data-stu-id="494e0-193">The new markup for the edit view is shown below:</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample17.cshtml)]

<span data-ttu-id="494e0-194">Criar exibição requer uma cadeia de caracteres vazia para impedir que o primeiro item a SelectList que está sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="494e0-194">The Create view requires an empty string to prevent the first item in the SelectList from being displayed.</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample18.cshtml)]

<span data-ttu-id="494e0-195">Criar um novo álbum e editar um álbum para verificar que as alterações estão funcionando.</span><span class="sxs-lookup"><span data-stu-id="494e0-195">Create a new album and edit an album to verify the changes work.</span></span> <span data-ttu-id="494e0-196">Teste o código de edição, selecionando um álbum com um gênero diferente Rock.</span><span class="sxs-lookup"><span data-stu-id="494e0-196">Test the edit code by selecting an album with a genre other than Rock.</span></span>

### <a name="using-a-view-model-with-the-dropdownlist-helper"></a><span data-ttu-id="494e0-197">Usando um modelo de exibição com o auxiliar DropDownList</span><span class="sxs-lookup"><span data-stu-id="494e0-197">Using a View Model with the DropDownList Helper</span></span>

<span data-ttu-id="494e0-198">Criar uma nova classe na pasta ViewModels denominada `AlbumSelectListViewModel`.</span><span class="sxs-lookup"><span data-stu-id="494e0-198">Create a new class in the ViewModels folder named `AlbumSelectListViewModel`.</span></span> <span data-ttu-id="494e0-199">Substitua o código no `AlbumSelectListViewModel` classe com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="494e0-199">Replace the code in the `AlbumSelectListViewModel` class with the following:</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample19.cs)]

<span data-ttu-id="494e0-200">O `AlbumSelectListViewModel` construtor usa um álbum, uma lista de artistas e gêneros e cria um objeto que contém o álbum e um `SelectList` para artistas e gêneros.</span><span class="sxs-lookup"><span data-stu-id="494e0-200">The `AlbumSelectListViewModel` constructor takes an album, a list of artists and genres and creates an object containing the album and a `SelectList` for genres and artists.</span></span>

<span data-ttu-id="494e0-201">Compilar o projeto para que o `AlbumSelectListViewModel` está disponível quando criamos uma exibição na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="494e0-201">Build the project so the `AlbumSelectListViewModel` is available when we create a view in the next step.</span></span>

<span data-ttu-id="494e0-202">Adicionar uma `EditVM` método para o `StoreManagerController`.</span><span class="sxs-lookup"><span data-stu-id="494e0-202">Add an `EditVM` method to the `StoreManagerController`.</span></span> <span data-ttu-id="494e0-203">O código completo é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-203">The completed code is shown below.</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample20.cs)]

<span data-ttu-id="494e0-204">Clique com botão direito `AlbumSelectListViewModel`, selecione **resolver**, em seguida, **usando MvcMusicStore.ViewModels;**.</span><span class="sxs-lookup"><span data-stu-id="494e0-204">Right click `AlbumSelectListViewModel`, select **Resolve**, then **using MvcMusicStore.ViewModels;**.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image9.png)

<span data-ttu-id="494e0-205">Como alternativa, você pode adicionar a seguinte instrução using:</span><span class="sxs-lookup"><span data-stu-id="494e0-205">Alternatively, you can add the following using statement:</span></span>

[!code-csharp[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample21.cs)]

<span data-ttu-id="494e0-206">Clique com botão direito `EditVM` e selecione **adicionar exibição**.</span><span class="sxs-lookup"><span data-stu-id="494e0-206">Right click `EditVM` and select **Add View**.</span></span> <span data-ttu-id="494e0-207">Use as opções abaixo.</span><span class="sxs-lookup"><span data-stu-id="494e0-207">Use the options shown below.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image10.png)

<span data-ttu-id="494e0-208">Selecione **adicionar**, em seguida, substitua o conteúdo do *Views\StoreManager\EditVM.cshtml* arquivo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="494e0-208">Select **Add**, then replace the contents of the *Views\StoreManager\EditVM.cshtml* file with the following:</span></span>

[!code-cshtml[Main](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/samples/sample22.cshtml)]

<span data-ttu-id="494e0-209">O `EditVM` marcação é muito semelhante ao valor original `Edit` marcação com as seguintes exceções.</span><span class="sxs-lookup"><span data-stu-id="494e0-209">The `EditVM` markup is very similar to the original `Edit` markup with the following exceptions.</span></span>

- <span data-ttu-id="494e0-210">Propriedades de modelo de `Edit` exibição têm o formato `model.property`(por exemplo, `model.Title` ).</span><span class="sxs-lookup"><span data-stu-id="494e0-210">Model properties in the `Edit` view are of the form `model.property`(for example, `model.Title` ).</span></span> <span data-ttu-id="494e0-211">Propriedades de modelo de `EditVm` exibição têm o formato `model.Album.property`(por exemplo, `model.Album.Title`).</span><span class="sxs-lookup"><span data-stu-id="494e0-211">Model properties in the `EditVm` view are of the form `model.Album.property`(for example, `model.Album.Title`).</span></span> <span data-ttu-id="494e0-212">Isso ocorre porque o `EditVM` exibição é passada um contêiner um `Album`, não um `Album` como no `Edit` exibição.</span><span class="sxs-lookup"><span data-stu-id="494e0-212">That's because the `EditVM` view is passed a container for an `Album`, not an `Album` as in the `Edit` view.</span></span>
- <span data-ttu-id="494e0-213">O **DropDownList** segundo parâmetro é proveniente do modelo de exibição, não o **ViewBag**.</span><span class="sxs-lookup"><span data-stu-id="494e0-213">The **DropDownList** second parameter comes from the view model, not the **ViewBag**.</span></span>
- <span data-ttu-id="494e0-214">O **BeginForm** auxiliar a `EditVM` exibição explicitamente envia de volta para o `Edit` método de ação.</span><span class="sxs-lookup"><span data-stu-id="494e0-214">The **BeginForm** helper in the `EditVM` view explicitly posts back to the `Edit` action method.</span></span> <span data-ttu-id="494e0-215">Postando de volta para o `Edit` ação, não temos que gravar um `HTTP POST EditVM` ação e pode reutilizar o `HTTP POST` `Edit` ação.</span><span class="sxs-lookup"><span data-stu-id="494e0-215">By posting back to the `Edit` action, we don't have to write an `HTTP POST EditVM` action and can reuse the `HTTP POST` `Edit` action.</span></span>

<span data-ttu-id="494e0-216">Execute o aplicativo e editar um álbum.</span><span class="sxs-lookup"><span data-stu-id="494e0-216">Run the application and edit an album.</span></span> <span data-ttu-id="494e0-217">Altere a URL para usar `EditVM`.</span><span class="sxs-lookup"><span data-stu-id="494e0-217">Change the URL to use `EditVM`.</span></span> <span data-ttu-id="494e0-218">Alterar um campo e pressione a **salvar** botão para verificar o código está funcionando.</span><span class="sxs-lookup"><span data-stu-id="494e0-218">Change a field and hit the **Save** button to verify the code is working.</span></span>

![](examining-how-aspnet-mvc-scaffolds-the-dropdownlist-helper/_static/image11.png)

### <a name="which-approach-should-you-use"></a><span data-ttu-id="494e0-219">Qual abordagem você deve usar?</span><span class="sxs-lookup"><span data-stu-id="494e0-219">Which Approach Should You Use?</span></span>

<span data-ttu-id="494e0-220">Todas as três abordagens mostradas são acceptible.</span><span class="sxs-lookup"><span data-stu-id="494e0-220">All three approaches shown are acceptible.</span></span> <span data-ttu-id="494e0-221">Muitos desenvolvedores preferem passagem explictily o `SelectList` para o `DropDownList` usando o `ViewBag`.</span><span class="sxs-lookup"><span data-stu-id="494e0-221">Many developers prefer to explictily pass the `SelectList` to the `DropDownList` using the `ViewBag`.</span></span> <span data-ttu-id="494e0-222">Essa abordagem tem a vantagem adicional de fornecer a flexibilidade de usar um nome mais apropriado para a coleção.</span><span class="sxs-lookup"><span data-stu-id="494e0-222">This approach has the added advantage of giving you the flexibility of using a more appropriate name for the collection.</span></span> <span data-ttu-id="494e0-223">Uma limitação é que você não pode nomear o `ViewBag SelectList` o mesmo nome que a propriedade do modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="494e0-223">The one caveat is you cannot name the `ViewBag SelectList` object the same name as the model property.</span></span>

<span data-ttu-id="494e0-224">Alguns desenvolvedores preferem a abordagem de ViewModel.</span><span class="sxs-lookup"><span data-stu-id="494e0-224">Some developers prefer the ViewModel approach.</span></span> <span data-ttu-id="494e0-225">Outros considere mais detalhado marcação e o código HTML gerado do ViewModel abordagem uma desvantagem.</span><span class="sxs-lookup"><span data-stu-id="494e0-225">Others consider the the more verbose markup and generated HTML of the ViewModel approach a disadvantage.</span></span>

<span data-ttu-id="494e0-226">Nesta seção aprendemos três abordagens para usar o **DropDownList** com dados de categoria.</span><span class="sxs-lookup"><span data-stu-id="494e0-226">In this section we have learned three approaches to using the **DropDownList** with category data.</span></span> <span data-ttu-id="494e0-227">Na próxima seção, mostraremos como adicionar uma nova categoria.</span><span class="sxs-lookup"><span data-stu-id="494e0-227">In the next section, we'll show how to add a new category.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="494e0-228">[Anterior](using-the-dropdownlist-helper-with-aspnet-mvc.md)
[Próximo](adding-a-new-category-to-the-dropdownlist-using-jquery-ui.md)</span><span class="sxs-lookup"><span data-stu-id="494e0-228">[Previous](using-the-dropdownlist-helper-with-aspnet-mvc.md)
[Next](adding-a-new-category-to-the-dropdownlist-using-jquery-ui.md)</span></span>