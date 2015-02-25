# GrowthAnalytics Class

## `+ (GrowthAnalytics *) sharedInstance;`
Return GrowthAnalytics instance.

##  `- (void)initializeWithApplicationId:(NSString *)applicationId credentialId:(NSString *)credentialId;`
initialize the GrowthAnalytics instance.

### Parameters
|Key|Value|
|:--|:--|
|applicationId|Application ID|
|credentialId|Credential ID for authentication|


## `- (void)track:(NSString *)eventId;`
## `- (void)track:(NSString *)eventId;`
## `- (void)track:(NSString *)eventId properties:(NSDictionary *)properties;`
## `- (void)track:(NSString *)eventId option:(GATrackOption)option;`
## `- (void)track:(NSString *)eventId properties:(NSDictionary *)properties option:(GATrackOption)option;`

## `- (void)tag:(NSString *)tagId;`
## `- (void)tag:(NSString *)tagId value:(NSString *)value;`

## `- (void)open;`
## `- (void)close;`
## `- (void)purchase:(int)price setCategory:(NSString *)category setProduct:(NSString *)product;`

## `- (void)setUserId:(NSString *)userId;`
## `- (void)setName:(NSString *)name;`
## `- (void)setAge:(int)age;`
## `- (void)setGender:(GAGender)gender;`
## `- (void)setLevel:(int)level;`
## `- (void)setDevelopment:(BOOL)development;`
## `- (void)setDeviceModel;`
## `- (void)setOS;`
## `- (void)setLanguage;`
## `- (void)setTimeZone;`
## `- (void)setTimeZoneOffset;`
## `- (void)setAppVersion;`
## `- (void)setRandom;`
## `- (void)setAdvertisingId:(NSString *)idfa;`
## `- (void)setBasicTags;`

## `- (GBLogger *)logger;`
## `- (GBHttpClient *)httpClient;`
## `- (GBPreference *)preference;`