%%
googleUsers = Animated_Tv_Series.GoogleUsers;
imdb = Animated_Tv_Series.IMDb;
figure(5);
scatter(imdb, googleUsers, 'filled');
title("IMDb vs puntajes de usuarios");
xlabel("IMDb");
ylabel("Puntajes de usuarios de Google");
%%
originalChannel = Animated_Tv_Series.OriginalChannel;
figure(6);
histogram(originalChannel, 'DisplayOrder','descend', 'NumDisplayBins', 10);
title("Histograma de canales originales")
%%
channelCategories = categories(originalChannel);
channelCount = countcats(originalChannel);
[sortedChannels, channelIdx] = sort(channelCount, 'descend');
sortedChannelNames = channelCategories(channelIdx);
firstChannels = sortedChannels(1:10);
firstChannelNames = sortedChannelNames(1:10);
figure(7);
piechart(firstChannels, firstChannelNames);
title("Programas por canal original");
