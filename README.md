### Olá, Me chamo Matheus 👋

- 🌱 Estudando ReactJS
- 🤔 Procuro por pessoas que queiram desenvolver aplicações
- 📫 Contato: matheus.souza74work@gmail.com
- 😄 Pronomes: ele/dele


 <div>
  <a href="https://github.com/Math-cod3">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=Math-cod3&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Math-cod3&layout=compact&langs_count=7&theme=dark"/>
</div>
 
  <img src="https://komarev.com/ghpvc/?username=Math-cod3&color=green" alt="Math-cod3" /> 
 
 <?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:vm="clr-namespace:Xamarin.Theming.ViewModels"
             mc:Ignorable="d"
             x:DataType="vm:LoginPageViewModel"
             x:Class="Xamarin.Theming.Views.LoginPage"
             BackgroundColor="{DynamicResource CorDeFundo}"
             NavigationPage.HasNavigationBar="False">
    <ContentPage.Content>
        <Grid VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">

            <Grid.RowDefinitions>
                <RowDefinition Height="50*"/>
                <RowDefinition Height="42*"/>
                <RowDefinition Height="8*"/>
            </Grid.RowDefinitions>
            
            <Label Grid.Row="0"
                   Text="Login animado! ✨"
                   FontAttributes="Bold"
                   TextColor="{DynamicResource CorPrimariaTexto}"
                   HorizontalOptions="CenterAndExpand"
                   VerticalOptions="CenterAndExpand"
                   FontSize="38"/>

            <StackLayout Orientation="Vertical" Margin="50,0,50,0" Grid.Row="1">
                <Label HorizontalOptions="CenterAndExpand"
                           Margin="0,0,0,15"
                           Text="Faça login para continuar"
                           TextColor="{DynamicResource CorPrimariaTexto}"
                           FontSize="14" />

                <Entry Style="{StaticResource EntryEstiloLogin}"
                           Text="{Binding Username, Mode=TwoWay}"
                           IsEnabled="{Binding IsNotBusy}"
                           ReturnType="Next"
                           Placeholder="Usuário"/>

                <Entry Style="{StaticResource EntryEstiloLogin}" 
                           Text="{Binding Password, Mode=TwoWay}"
                           IsEnabled="{Binding IsNotBusy}"
                           ReturnType="Go"
                           ReturnCommand="{Binding LoginCommand}"
                           Placeholder="Senha" 
                           IsPassword="True"/>

                <Grid HorizontalOptions="FillAndExpand" HeightRequest="50" Padding="0" Margin="0">
                    <Button x:Name="LoginButton"
                            HorizontalOptions="FillAndExpand"
                            BackgroundColor="{DynamicResource ButtonCorDeFundo}"
                            TextColor="{DynamicResource ButtonCorTexto}"
                            Command="{Binding LoginCommand}"
                            Text="Entrar"
                            CornerRadius="25"/>

                    <Frame x:Name="LoginFrame"
                               BackgroundColor="{DynamicResource ButtonCorDeFundo}"
                               IsVisible="False"
                               CornerRadius="25"
                               Padding="0" 
                               Margin="0">

                        <ActivityIndicator Color="{DynamicResource ButtonCorTexto}"
                                           IsRunning="{Binding IsBusy}"
                                           PropertyChanged="OnActivityIndicatorPropertyChanged"/>
                    </Frame>
                </Grid>
            </StackLayout>
        </Grid>
    </ContentPage.Content>
</ContentPage>
