# NWEN243-Ass1-split-method

char **splitter(char *text, int key) {
  char **splitText = (char**)malloc(sizeof(char)*key);
  int splitLength = strlen(text)/key+1;
  for(int i = 0; i < key; i++){
    char *nDivision = (char*)malloc(sizeof(char)*splitLength+1);
    splitText[i] = &nDivision[0];
  }
  int splitCount = 0;
  int row = 0;  //will count how far we are in the string subsections
  for(int i = 0; i < strlen(text); i++){
    if(splitCount == key){
      splitCount = 0;
      row++;
    }
    splitText[splitCount][row] = text[i];
    splitCount++;
  }
  for(int i = 0; i < key; i++){
   splitText[i][splitLength] = '\0';
  }
  return splitText;

}
