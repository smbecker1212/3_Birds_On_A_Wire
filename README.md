3_Birds_On_A_Wire
=================

Dat Project

% Loads selected map
cityMap = imread('Boston_ScreenShot.jpg');
% colors every 25th row of pixels white
cityMap(25:25:end,:,:) = 255;
% colors every 25th column of pixels white
cityMap(:,25:25:end,:) = 255;
% displays map
imshow(cityMap);

hold on
for i = 1:10
%     
deviceSelectMsg = {'Select a model solar panel or wind turbine:'};
dselchoices = {'Sunforce 50048', 'Sunforce 39810', 'Instapark SPCC-5W',...
    'Instapark SP-100W', 'Instapark SPCC-30W', 'Instapark SP-10W', ...
    'Ramsond 100SP', 'Epcom WK50-12', 'Sun Power E18', 'Sun Power T5', ...
    'Windmax HY 1000-5', 'Windmax HY 400', 'GudCraft WG400', ...
    'GudCraft WG700', 'All Power America APWT400A', 'Sunforce 45444', ...
    'Sunforce 44444', 'Windy Nation WCK-750'};
deviceChoice = menu(deviceSelectMsg,dselchoices);

deviceChoices(i) = deviceChoice;

switch (deviceChoice)
    case 1
        boxColor = 'y';
    case 2
        boxColor = 'b';
    case 3
        boxColor = 'g';
    case 4
        boxColor = 'g';
    case 5
        boxColor = 'g';
    case 6
        boxColor = 'g';
    case 7
        boxColor = 'g';
    case 8
        boxColor = 'b';
    case 9 
        boxColor = 'g';
    case 10
        boxColor = 'g';
    case 11
        boxColor = 'r';
    case 12
        boxColor = 'r';
    case 13
        boxColor = 'r';
    case 14
        boxColor = 'r';
    case 15
        boxColor = '';
    case 16
        boxColor = 'c';
    case 17
        boxColor = 'r';
    case 18 
        boxColor = 'c';
        
end



[x,y] = getpts(figure(1));
startX = x-mod(x,25)+1;
endX = x - mod(x,25) + 24;
startY = y-mod(y,25)+1;
endY = y - mod(y,25) + 24;
[x,y] = meshgrid(startX:endX,startY:endY);
figure(1);
plot(x,y,boxColor);
if i == 10
    msgbox('Your limit of 10 has been reached', 'Limit Reached');
    break
end
continueMsg = {'Would you like to continue placing solar panels or', ...
    'wind turbines? (you may place a maximum of 10)'};
continueChoices = {'Indeed', 'No thank you'};
continueMenu = menu(continueMsg, continueChoices);

if continueMenu == 2
    break
end

end


        
        

